# LVM Lab on VirtualBox

## Environment

### Existing OS Disk

```bash
lsblk
```

Output:

```text
sda    25G   <- Ubuntu OS Disk
├─sda2       <- /boot/efi
└─sda3       <- /
```

### Added Practice Disks

Created 3 VirtualBox disks:

```text
sdb    1G
sdc    1G
sdd    1G
```

Verify:

```bash
lsblk
```

---

# 1. Creating and Mounting a Volume Using LVM

## Step 1: Install LVM

```bash
sudo apt update
sudo apt install lvm2
```

Verify:

```bash
which pvcreate
```

---

## Step 2: Create Physical Volumes (PV)

Convert disks into LVM Physical Volumes.

```bash
sudo pvcreate /dev/sdb /dev/sdc
```

Verify:

```bash
sudo pvs
```

Example:

```text
PV         VG   Fmt  Attr PSize PFree
/dev/sdb        lvm2 ---  1.00g 1.00g
/dev/sdc        lvm2 ---  1.00g 1.00g
```

---

## Step 3: Create Volume Group (VG)

Combine the physical volumes into one storage pool.

```bash
sudo vgcreate vggp1 /dev/sdb /dev/sdc
```

Verify:

```bash
sudo vgs
```

Example:

```text
VG     #PV #LV VSize VFree
vggp1    2   0 1.99g 1.99g
```

---

## Step 4: Create Logical Volume (LV)

Create a 500 MB logical volume.

```bash
sudo lvcreate -L 500M -n lv_data vggp1
```

Verify:

```bash
sudo lvs
```

Example:

```text
LV       VG     LSize
lv_data  vggp1  500.00m
```

---

## Step 5: Create Filesystem

Format the logical volume.

```bash
sudo mkfs.ext4 /dev/vggp1/lv_data
```

---

## Step 6: Create Mount Point

```bash
sudo mkdir /mnt/lab
```

---

## Step 7: Mount Logical Volume

```bash
sudo mount /dev/vggp1/lv_data /mnt/lab
```

Verify:

```bash
df -h
```

or

```bash
mount | grep lab
```

---

## Step 8: Test

```bash
echo "Hello LVM" > /mnt/lab/test.txt

cat /mnt/lab/test.txt
```

Expected:

```text
Hello LVM
```

---

# 2. Creating and Mounting a Normal Volume (Without LVM)

Using disk:

```text
/dev/sdd
```

---

## Step 1: Create Filesystem

```bash
sudo mkfs.ext4 /dev/sdd
```

---

## Step 2: Create Mount Point

```bash
sudo mkdir /mnt/disk1
```

---

## Step 3: Mount Disk

```bash
sudo mount /dev/sdd /mnt/disk1
```

---

## Step 4: Verify

```bash
df -h
```

or

```bash
mount | grep disk1
```

---

## Step 5: Test

```bash
echo "Normal Disk" > /mnt/disk1/test.txt

cat /mnt/disk1/test.txt
```

---

# 3. Extending a Logical Volume

Current setup:

```text
VG = vggp1
LV = lv_data
```

VG still has free space available.

---

## Check Free Space

```bash
sudo vgs
```

Example:

```text
VG     VSize VFree
vggp1  1.99g 1.49g
```

---

## Extend Logical Volume

Add 500 MB.

```bash
sudo lvextend -L +500M /dev/vggp1/lv_data
```

Verify:

```bash
sudo lvs
```

---

## Resize Filesystem

For ext4:

```bash
sudo resize2fs /dev/vggp1/lv_data
```

---

## Verify New Size

```bash
df -h
```

or

```bash
lsblk
```

---

# Useful LVM Commands

## Physical Volumes

```bash
sudo pvs
sudo pvdisplay
```

## Volume Groups

```bash
sudo vgs
sudo vgdisplay
```

## Logical Volumes

```bash
sudo lvs
sudo lvdisplay
```

## Block Devices

```bash
lsblk
```

## Mounted Filesystems

```bash
df -h
mount
```

---

# LVM Architecture

```text
Physical Disks
(/dev/sdb, /dev/sdc)
          │
          ▼
       PVs
 (Physical Volumes)
          │
          ▼
       VG
   (Volume Group)
          │
          ▼
       LV
  (Logical Volume)
          │
          ▼
      mkfs
          │
          ▼
      mount
          │
          ▼
     /mnt/lab
```

# AWS Mapping

VirtualBox:

```text
/dev/sdb
/dev/sdc
/dev/sdd
```

AWS EC2:

```text
/dev/xvdf
/dev/xvdg
/dev/xvdh
```

Commands remain exactly the same; only device names change.
