### Deleting and Recreating the Recovery Partition
This guide outlines a safe, command-line-driven method to extend a Windows 11 C: drive by deleting and recreating the recovery partition, avoiding risky data block moves. The workflow involves disabling the **Windows Recovery Environment** (WinRE), using **Diskpart** to delete the old partition, extending the C: drive while leaving a 1GB gap, and creating a new, compliant recovery partition, followed by re-enabling WinRE. This process ensures proper partition alignment and stability without relying on third-party tools.

This is the most reliable "professional" way to handle the Recovery Partition. By deleting and re-creating it, you ensure the partition is properly aligned at the very end of your new 128GB disk space, and Windows will automatically update its boot links.


#### Phase 1: Disable and Delete
1. Open the `Start Menu`, type `cmd`, right-click it, and select `Run as Administrator`.

2. Turn off the Recovery Environment:
```
reagentc /disable
```
(*This moves the recovery boot file back to your C: drive temporarily so it doesn't get deleted.*)

3. Enter `Diskpart`:
```
diskpart
```
4. Identify and Delete the old partition:
    * `list disk` (Find your main disk, usually Disk 0)
    * `select disk 0`
    * `list partition` (Identify the "Recovery" partition, e.g., Partition 4)
    * `select partition 4`
    * `delete partition override`

5. Extend your C: Drive (leaving space for the new one):
    * `select partition 3` (Select your C: drive partition)
    * `extend size=127000`
    (*Note: If your disk is exactly 128GB, extending to ~127GB ensures there is exactly 1GB of "Unallocated Space" left at the end.*)

6. `exit`


#### Phase 2: Create the New Recovery Partition
Now we create a clean, modern recovery partition in that 1GB gap.

1. Back in the Administrator CMD, enter Diskpart again:
```
diskpart
```

2. Create the partition:
    * `select disk 0`
    * `create partition primary`
    * `format quick fs=ntfs label="Recovery"`

3. Set the "ID" so Windows knows it's a System Partition:
    * `set id=de94bba4-06d1-4d40-a16a-bfd50179d6ac`
    * `gpt attributes=0x8000000000000001`

4. `exit`


#### Phase 3: Re-link and Enable
Now we tell Windows to put the recovery tools back into this new home.

1. Enable the Recovery Environment:
```
reagentc /enable
```

2. Verify the Status:
```
reagentc /info
```

You should now see Windows RE status: Enabled and the location should point to the very last partition on the disk.


#### Why this is better than moving with GParted:
* Alignment: Windows creates the partition with the correct sector alignment for your SSD.
* No Corruption: You aren't "shifting" data blocks, so there is zero risk of filesystem corruption.
* Automatic: The reagentc /enable command automatically finds the new partition and updates the ReAgent.xml file for you.

Crucial Checklist before starting:

* Take a VirtualBox Snapshot named "Before Partition Edit".
* Ensure your VM disk was already resized to 128GB in the VirtualBox Media Manager.

Would you like me to explain how to calculate the exact number for the extend size= command based on your specific disk size?

