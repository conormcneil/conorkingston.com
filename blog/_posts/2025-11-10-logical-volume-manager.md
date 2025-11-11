---
layout: post
title: "Logical Volume Manager with Linux"
date: 2025-11-10
summary: Using Logical Volume Manager to configure block storage in Linux systems.
tags: storage
---

## Terms

**Thin provisioning** is a feature that guarantees efficient use of storage space by allocating only what is needed and by storing data at adjacent locations.

**Virtual Data Optimizer** capitalizes on thin provisioning, de-duplication, and compression technologies to conesrve storage space, improve data throughput, and save money.

The **Logical Volume Manager** solution sets up an abstraction layer between the operating system and the storage hardware. It utilizes virtual objects for storage pooling and allocation.

A **Physical Volume** (PV) is a block storage device, such as a *partition* or an *entire disk* that has been initialized and brought under LVM control.

A **Volume Group** is a storage pool composed of the aggregated space from all the physical volumes that have been added to it, which is then used to build logical volumes.

A **Physical Extent** (PE) is the smallest unit of storage on a physical volume. PEs represent *actual* disk space on real devices.

A **Logical Volume** (LV) is a virtual partition carved out of a volume group. It acts like a traditional disk partition but it is much more flexible.

A **Logical Extent** is the smallest unit of storage allocation on a logical volume. Every LE maps 1:1 to a physical extent in the volume group. They represent the *logical* view of storage that the LV uses.

## LVM Operations and Commands

The LVM toolset provides administrative commands to carry out disk and volume management operations.

#### Create and Remove Operations

| pvcreate/pvremove || (Un)initializes a disk or partition for LVM use. |
| vgcreate/vgremove || Creates/removes a volume group.   |
| lvcreate/lvremove || Creates/removes a logical volume. |

#### Extend and Reduce Operations

| vgextend/vgreduce || Adds/removes a physical volume to/from a volume group. |
| lvextend/lvreduce || Extends/reduces the size of a physical volume. |
| lvresize          || Resizes a logical volume. With the -r option, this command calls the fsadm command to resize the underlying file system as well. |

#### Rename Operations

| vgrename || Renames a volume group. |
| lvrename || Renames a logical volume. |

#### List and Display Operation

| pvs/pvdisplay || Lists/displays physical volume information. |
| vgs/vgdisplay || Lists/displays volume group information. |
| lvs/lvdisplay || Lists/displays logical volume information. |