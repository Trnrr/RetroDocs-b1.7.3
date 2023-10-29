---
title: Permissions
---

# Permissions

??? danger "Wildcard "*" use is not recommended!"
    The Wildcard character "*" allows you to grant all permissions based on the supplied node. For example, `lockette.user.*` would grant `lockette.user.create.chest`, `lockette.user.create.furnace`, etc. This is problematic because it would also grant `lockette.user.bypass`. If this was a real permission, this may not be something a normal user should have. It's recommended to apply each permission node individually, instead of using the wildcard.

 Permission Plugins | Version | Supported
--------------------|---------|-----------
GroupManager        |         | Yes 
PermissionsEX       | 1.13    | No 


## Permission List
The permissions listed below were taken from the Lockette v1.4 jar file.


=== "Permissions"
    Permission | Role | Command | Description
    -----------|------|---------|------------
    lockette.create.all|User||Allow user to lock all lockable blocks.
    lockette.user.create.chest|User||Allow user to lock chests.
    lockette.user.create.furnace|User||Allow user to lock furnaces.
    lockette.user.create.dispenser|User||Allow user to lock dispencers.
    lockette.user.create.trapdoor|User||Allow user to lock trapdoors.
    lockette.user.create.doorUser|User||Allow user to lock doors.
    lockette.admin.create.chest|Admin|
    lockette.admin.create.furnace|Admin|
    lockette.admin.create.dispenser|Admin|
    lockette.admin.create.trapdoor|Admin|
    lockette.admin.create.door|Admin|
    lockette.admin.break|Admin|
    lockette.admin.reload|Admin|`/lockette reload`|
    lockette.admin.bypass|Admin|
    lockette.admin.snoop|Admin|

=== "RAW"
    ```
    lockette.create.all
    lockette.user.create.chest
    lockette.user.create.furnace
    lockette.user.create.dispenser
    lockette.user.create.trapdoor
    lockette.user.create.door
    lockette.admin.create.chest
    lockette.admin.create.furnace
    lockette.admin.create.dispenser
    lockette.admin.create.trapdoor
    lockette.admin.create.door
    lockette.admin.break
    lockette.admin.reload
    lockette.admin.bypass
    lockette.admin.snoop
    ```