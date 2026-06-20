🚀 Hands-On Learning: Linux LVM (Logical Volume Manager) on VirtualBox

Today I built a small LVM lab to understand how enterprise Linux storage management works and how the same concepts are used with AWS EBS volumes.

### What I learned

✅ Added multiple virtual disks to a Linux VM

✅ Explored block devices using:

```bash
lsblk
df -h
```

✅ Learned the difference between:

* Physical Disks
* Physical Volumes (PV)
* Volume Groups (VG)
* Logical Volumes (LV)

### LVM Workflow

```text
Physical Disks
     ↓
pvcreate
     ↓
Physical Volumes (PV)
     ↓
vgcreate
     ↓
Volume Group (VG)
     ↓
lvcreate
     ↓
Logical Volume (LV)
     ↓
mkfs.ext4
     ↓
mount
```

### Commands Practiced

```bash
sudo pvcreate /dev/sdb /dev/sdc
sudo vgcreate vggp1 /dev/sdb /dev/sdc
sudo lvcreate -L 500M -n lv_data vggp1
sudo mkfs.ext4 /dev/vggp1/lv_data
sudo mount /dev/vggp1/lv_data /mnt/lab
```

### Key Takeaways

🔹 A Physical Volume (PV) is a disk prepared for LVM.

🔹 A Volume Group (VG) combines multiple disks into a single storage pool.

🔹 A Logical Volume (LV) acts like a flexible virtual partition.

🔹 LVM allows storage expansion without recreating filesystems.

🔹 The same concepts can be applied to Amazon EBS volumes attached to EC2 instances.

### AWS Connection

VirtualBox Lab:

```text
/dev/sdb
/dev/sdc
```

AWS EC2:

```text
/dev/xvdf
/dev/xvdg
```

The storage architecture remains the same—only the device names change.

Learning by building small labs is one of the best ways to understand Linux internals and cloud infrastructure.

#Linux #LVM #DevOps #AWS #EC2 #EBS #CloudComputing #SystemAdministration #LinuxAdministration #VirtualBox #LearningInPublic
