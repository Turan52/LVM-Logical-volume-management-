# LVM-Logical-volume-management-
Logical volume management (LVM) is a form of storage virtualization that offers system administrators a more flexible approach to managing disk storage space than traditional partitioning. This type of virtualization tool is located within the device-driver stack on the operating system.

LVM is used for the following purposes:

Creating single logical volumes of multiple physical volumes or entire hard disks (somewhat similar to RAID 0, but more similar to JBOD), allowing for dynamic volume resizing.
Managing large hard disk farms by allowing disks to be added and replaced without downtime or service disruption, in combination with hot swapping.
On small systems (like a desktop), instead of having to estimate at installation time how big a partition might need to be, LVM allows filesystems to be easily resized as needed.
Performing consistent backups by taking snapshots of the logical volumes.
Encrypting multiple physical partitions with one password.
LVM can be considered as a thin software layer on top of the hard disks and partitions, which creates an abstraction of continuity and ease-of-use for managing hard drive replacement, repartitioning and backup.

LVM Storage Management Structures
LVM functions by layering abstractions on top of physical storage devices. The basic layers that LVM uses, starting with the most primitive, are:

Physical Volumes: The LVM utility prefix for physical volumes is pv.... This physicallyl blocks devices or other disk-like devices (for example, other devices created by device mapper, like RAID arrays) and are used by LVM as the raw building material for higher levels of abstraction. Physical volumes are regular storage devices. LVM writes a header to the device to allocate it for management.

Volume Groups: The LVM utility prefix for volume groups is vg.... LVM combines physical volumes into storage pools known as volume groups. Volume groups abstract the characteristics of the underlying devices and function as a unified logical device with combined storage capacity of the component physical volumes.

Logical Volumes: The LVM utility prefix for logical volumes is lv..., generic LVM utilities might begin with lvm.... A volume group can be sliced up into any number of logical volumes. Logical volumes are functionally equivalent to partitions on a physical disk, but with much more flexibility. Logical volumes are the primary component that users and applications will interact with.

LVM can be used to combine physical volumes into volume groups to unify the storage space available on a system. Afterwards, administrators can segment the volume group into arbitrary logical volumes, which act as flexible partitions.
