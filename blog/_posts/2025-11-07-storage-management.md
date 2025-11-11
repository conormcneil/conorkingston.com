---
layout: post
title: "Storage Management with Linux"
date: 2025-11-07
summary: Managing storage
tags: storage
---

Data is stored on disks that are logically divided into **partitions**. 
- A partition can exist on a portion of a disk, an entire disk, or it may span multiple disks.
- Each partition is managed independent of other partitions.
- A partition may contain a *file system* or *swap space*.
- Partitioning information is stored at special disk locations that the system references at boot time.

## Partitions

#### Master Boot Record

- For use with **BIOS**-based systems
- Three partition types: *primary*, *logical*, *extended*
- Supports up to 14 partitions per disk (3 primary, 11 logical)
- Cannot support disks larger than 2TB
- 512-byte sector size, 32-bit
- Non-redundant; stores a single copy of the partition information on the first sector of the disk

#### GUID Partition Table

- For use with **UEFI**-based systems
- Supports up to 128 partitions per disk
- Supports disks larger than 2TB
- 4KB sector size, 64-bit
- Redundant; stores a second copy of the partition information before the end of the disk
- Works also with BIOS-based systems

## Management Tools

#### parted

*parted* (*partition editor*) can be used to partition disks interactively or directly from the command prompt.

It understands and supports both MBR and GUID partition schemes.

| print     || Displays the partition table that includes disk geometry and partition number, start and end, size, type, file system type, and relevant flags. |
| mklabel   || Applies a label to the disk. Common labels are **msdos** and **gpt**. |
| mkpart    || Makes a new partition. |
| name      || Assigns a name to a partition. |
| rm        || Removes the specified partition. |

#### gdisk

The *gdisk* (*GPT disk*) utility is a text-based, menu-driven program that partitions disks using the GPT format. The main interface of *gdisk* can be invoked by specifying a disk device name with the command (such as */dev/sdc*).