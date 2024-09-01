Subvolumes in Btrfs are similar to directories but have unique properties that make them act like independent file systems within a Btrfs partition. They can be used to isolate data, manage [[snapshots]] more efficiently, and provide flexibility in organizing the file system.

**Key Characteristics**:

- **Independence**: Each subvolume can have its own set of attributes, snapshots, and [[mount]] options. They operate independently of each other while sharing the same storage pool.
- **Snapshots**: Snapshots can be taken at the subvolume level, capturing the state of the subvolume at a specific point in time. These snapshots are space-efficient and can be used for backups, testing, or system recovery.
- **No Fixed Size**: Subvolumes do not have a fixed size and dynamically share space within the Btrfs file system. This makes them flexible for handling data growth.
- **Mountable**: Subvolumes can be mounted separately using specific mount points, allowing them to be managed and accessed independently.
- **Quota Support**: Subvolumes can have quotas set to limit the amount of space they can use, helping in managing disk space and preventing any single subvolume from consuming too much space.


**Commands**:
- **Creating a Subvolume**: 
  ```bash
  btrfs subvolume create /path/to/subvolume
  ```
- **Listing Subvolumes**: 
  ```bash
  btrfs subvolume list /path/to/mount
  ```
- **Taking a Snapshot**: 
  ```bash
  btrfs subvolume snapshot /source/path /dest/path
  ```


#linux #filesystems #storage 