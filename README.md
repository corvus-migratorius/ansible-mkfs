Role Name
=========

Create a filesystem on the target device (thinly wraps `community.general.filesystem` module).

Requirements
------------

Uses specific tools related to the fstype for creating or resizing a filesystem (`e2fsprogs`, `xfsprogs`, etc.).

Uses generic tools mostly related to the OS, like `blkid`.

Role Variables
--------------

`mkfs_device`: (string) device that the filesystem should be created on
`mkfs_type`: (string) type of the filesystem to be created
`mkfs_opts`: (string) a list of options to be passed to `mkfs` (*not* a YAML array)
`mkfs_state`: (string) `absent` or `present`
`mkfs_force`: (boolean) overwrite an existing fs if there is one (default: false)

Dependencies
------------

None

Example Playbook
----------------

```yaml
roles:
  - role: mkfs
    mkfs_device: "/dev/disk/by-id/my-disk
    mkfs_type: ext4
    mkfs_state: present
```


License
-------

BSD

Author Information
------------------

corvus-migratorius@proton.me
