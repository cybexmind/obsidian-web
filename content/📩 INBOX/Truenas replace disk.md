---
{"publish":true,"created":"2025-07-08T23:34:48.919+02:00","modified":"2025-07-08T23:39:08.355+02:00","cssclasses":""}
---

🏷 Tags:
➕ 

# TrueNAS Core

To replace a disk in a mirror pool in TrueNAS CORE, follow these steps:

1. Go to **Storage > Pools**.
2. Click the settings icon for your pool and select **Status** to open the Pool Status screen.
3. Click the icon for the disk you want to replace and select **Offline**. Confirm the action.
4. Once the disk status shows as Offline, physically remove the failed disk from your system.
5. Insert the replacement disk (it must be the same or greater capacity and not part of another pool).
6. In the Pool Status screen, open the options for the offline disk and click **Replace**.
7. Select the new disk and click **Replace Disk**. If the disk has existing data, you may need to use the **Force** option to wipe it.
8. The system will begin resilvering (rebuilding) the mirror. This process can take some time depending on the amount of data.
9. When resilvering is complete, your pool will return to Online status.


# TrueNAS Scale

To replace a disk in a mirror pool in TrueNAS SCALE, follow these steps:

10. **Take the failed disk offline:**
    
    - Go to the **Storage Dashboard** and click **Manage Devices** on the **Topology** widget for your pool.
    - Expand the VDEV and select the failed disk.
    - Click **Offline** on the **ZFS Info** widget to take the disk offline. Remove the disk from the system.
11. **Insert the replacement disk:**
    
    - Insert a new disk of equal or greater capacity into an available slot.
12. **Replace the disk in the pool:**
    
    - On the **_Poolname_ Devices** screen, click **Replace** on the **Disk Info** widget for the offline disk.
    - Select the new drive from the **Member Disk** dropdown list.
    - Click **Replace Disk**. If the new disk has data or partitions, select the **Force** option to wipe it.
13. **Wait for resilvering:**
    
    - TrueNAS will automatically start resilvering (rebuilding) the mirror. Wait for this process to complete before replacing any other disks.