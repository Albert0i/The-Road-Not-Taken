# Tutorial: Automating Oracle 19c Masking Policies with a Re‑Run Safe Procedure

Masking sensitive data in Oracle 19c is essential when developers and testers need access to realistic but anonymized datasets. Oracle provides **Dynamic Data Redaction (DBMS_REDACT)** for runtime masking, but managing hundreds of policies across dozens of tables can quickly become overwhelming.  

This tutorial shows you how to build a **metadata‑driven, re‑run safe procedure** that automatically applies masking policies to all sensitive columns. With this approach, you can maintain a single metadata table and call one procedure to enforce masking consistently across your environment.

---

## 🔹 Why Automate Masking Policies?
- **Scalability**: Large databases often have dozens of tables and hundreds of sensitive fields.  
- **Maintainability**: Instead of hand‑coding hundreds of `ADD_POLICY` calls, you define sensitive fields once in a metadata table.  
- **Re‑Run Safety**: The procedure drops existing policies if they exist, then re‑adds them, so you can run it multiple times without errors.  
- **Consistency**: All policies are applied uniformly, reducing human error.  

---

## 🔹 Step 1: Create the Metadata Table
This table acts as a catalog of sensitive columns. Each row defines the schema, table, column, policy name, mask type, and optional parameters.

```sql
CREATE TABLE SENSITIVE_COLUMNS (
  schema_name   VARCHAR2(30),
  table_name    VARCHAR2(30),
  column_name   VARCHAR2(30),
  policy_name   VARCHAR2(50),
  mask_type     VARCHAR2(20),   -- FULL, PARTIAL, REGEXP, NULLIFY
  mask_params   VARCHAR2(200)   -- optional parameters
);
```

Populate it with entries for each sensitive field:

```sql
INSERT INTO SENSITIVE_COLUMNS VALUES ('HR','EMPLOYEE','NAME','NAME_MASK_POLICY','FULL',NULL);
INSERT INTO SENSITIVE_COLUMNS VALUES ('HR','EMPLOYEE','ADDRESS','ADDR_MASK_POLICY','REGEXP','''[一-龥0-9]'',''#''');
INSERT INTO SENSITIVE_COLUMNS VALUES ('HR','EMPLOYEE','DOB','DOB_MASK_POLICY','PARTIAL','0,10,''XXXX-XX-XX''');
INSERT INTO SENSITIVE_COLUMNS VALUES ('HR','EMPLOYEE','NATIONAL_ID','NID_MASK_POLICY','PARTIAL','0,12,''XXXXXXXXXXXX''');
```

This table becomes your **single source of truth** for masking definitions.

---

## 🔹 Step 2: Create the Re‑Run Safe Procedure
Wrap the automation logic into a stored procedure. This procedure loops through the metadata table, drops existing policies if they exist, and re‑adds them with the latest definition.

```sql
CREATE OR REPLACE PROCEDURE APPLY_MASK_POLICIES AS
BEGIN
  FOR rec IN (SELECT * FROM SENSITIVE_COLUMNS) LOOP
    -- Drop policy if it exists
    BEGIN
      DBMS_REDACT.DROP_POLICY(
        object_schema => rec.schema_name,
        object_name   => rec.table_name,
        policy_name   => rec.policy_name
      );
    EXCEPTION WHEN OTHERS THEN NULL;
    END;

    -- Add policy based on mask_type
    DBMS_REDACT.ADD_POLICY(
      object_schema => rec.schema_name,
      object_name   => rec.table_name,
      column_name   => rec.column_name,
      policy_name   => rec.policy_name,
      function_type => CASE rec.mask_type
                         WHEN 'FULL'    THEN DBMS_REDACT.FULL
                         WHEN 'PARTIAL' THEN DBMS_REDACT.PARTIAL
                         WHEN 'REGEXP'  THEN DBMS_REDACT.REGEXP
                         WHEN 'NULLIFY' THEN DBMS_REDACT.NULLIFY
                       END,
      function_parameters => rec.mask_params,
      expression    => 'SYS_CONTEXT(''USERENV'',''SESSION_USER'') = ''DEV_USER'''
    );
  END LOOP;
END;
/
```

---

## 🔹 Step 3: Running the Procedure
Once created, you can run the procedure anytime:

```sql
EXEC APPLY_MASK_POLICIES;
```

or in DBeaver:

```sql
BEGIN
  APPLY_MASK_POLICIES;
END;
/
```

Each run will:
1. Drop existing policies (if they exist).  
2. Re‑add them with the latest definitions from the metadata table.  
3. Ensure all sensitive columns are consistently masked.  

---

## 🔹 Step 4: Testing the Policies
After running the procedure, query the masked table:

```sql
SELECT NAME, ADDRESS, DOB, NATIONAL_ID FROM HR.EMPLOYEE;
```

- For `DEV_USER`, values appear masked (e.g., `张伟` → `**`, `北京市朝阳区建国路88号` → `#######88#`).  
- For other users (like `HR_ADMIN`), values remain visible.  

This confirms that the masking policies are applied correctly.

---

## 🔹 Step 5: Scaling to Dozens of Tables
With this approach:
- You only need to maintain the **SENSITIVE_COLUMNS metadata table**.  
- Adding a new sensitive field = one new row in the table.  
- The procedure handles the rest.  
- Even with 60 tables × 4 columns (240+ policies), the script remains compact and maintainable.

---

## 🔹 Best Practices
- **Consistent Policy Names**: Use clear, unique names (`TABLE_COLUMN_MASK_POLICY`).  
- **Central Metadata Management**: Keep the metadata table updated as schemas evolve.  
- **Controlled Expressions**: Tailor the `expression` to specific users or roles.  
- **Audit Regularly**: Query `DBA_REDACT_POLICIES` to verify active policies.  
- **Version Control**: Store your metadata table and procedure definition in source control for traceability.  

---

## 🔹 Conclusion
By combining a **metadata table** with a **re‑run safe procedure**, you can manage hundreds of masking policies in Oracle 19c efficiently. This approach ensures:
- Scalability across many tables and columns.  
- Idempotency — safe to re‑run anytime.  
- Maintainability — one place to update definitions.  

Instead of hand‑coding hundreds of `ADD_POLICY` calls, you define sensitive fields once and let PL/SQL handle the rest. This is the professional way DBAs manage large‑scale redaction environments.

---

🪶 With this new procedure, you now have a **one‑command solution** (`EXEC APPLY_MASK_POLICIES;`) to enforce all masking policies consistently.  

Would you like me to also create a **companion procedure** (e.g., `DROP_ALL_MASK_POLICIES`) that clears everything out in one go, so you can reset the environment before applying fresh definitions?