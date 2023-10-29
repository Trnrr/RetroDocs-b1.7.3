---
title: Lockette
---
## Overview
??? warning "Documentation for this page is in progress."
    This plugins documentation is currently in progress. Please let us know if anything is incorrect.

 Name|Version|Author|License
-|-|-|-
Lockette|1.4|[Acru](https://bukkit.org/members/acru.12037/)|NPOSL-3.0

Lockette is a simple chest locking and protection plugin. Take a look at the [User Guide](#user-guide) to see how it works!

- [Bukkit Project Page](https://dev.bukkit.org/projects/lockette)
- [Bukkit Forum Archive](https://bukkit.org/threads/sec-lockette-simple-chest-and-door-lock-no-databases-moved-to-bukkitdev.4336/)

[Download on the Glass Repo](#){ .md-button  }

--------------------------------------------------------------------------------------------

## User Guide
Lockette allows users to lock chests.

While holding a sign, right click on a chest. This will place the sign on the chest and your username will be listed on line 2. You can add additional users by right clicking on the sign and then typing `/lockette 3 FriendsName`. You can also attach more signs to the chest to increase the user count.

### Commands

---
**`/lockette <line number> <text>`**  
:   Permission: N/A  
    *Edit's signs on locked containers. Right click on the sign to edit.*
---
**`/lockette fix`**  
:   Permission: N/A  
    *Fixes an automatic door that is in the wrong position. Look at the door to edit.*
---
**`/lockette reload`**  
:   Permission: lockette.admin.reload  
    *Reloads the configuration files, Operators only.*
---
**`/lockette version`**  
:   Permission: No permission node  
    *Reports Lockette version string.*

### Community Video Tutorials

**Video by:** Username here  
:   <iframe width="560" height="315" src="https://www.youtube.com/embed/sS8_AOuBqZE?si=Sz11jsifYtB-AKLO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

--------------------------------------------------------------------------------------------

## Permissions

??? danger "Wildcard "*" use is not recommended!"
    The Wildcard character "*" allows you to grant all permissions based on the supplied node. For example, `lockette.user.*` would grant `lockette.user.create.chest`, `lockette.user.create.furnace`, etc. This is problematic because it would also grant `lockette.user.bypass`. If this was a real permission, this may not be something a normal user should have. It's recommended to apply each permission node individually, instead of using the wildcard.

 Permission Plugins | Version | Supported
--------------------|---------|-----------
GroupManager        | 1.0(alpha-5) | Yes 
PermissionsEX       | 1.13    | No 
Permissions         | 2.7.4 | Yes


### Permission List
The permissions listed below were taken from the Lockette v1.4 jar file.


=== "Permissions"
    Permission |  Command or Notes
    -----------|-------------------
    lockette.create.all|Allow user to lock all containers.
    lockette.user.create.chest|Allow user to lock chests.
    lockette.user.create.furnace|Allow user to lock furnaces.
    lockette.user.create.dispenser|Allow user to lock dispencers.
    lockette.user.create.trapdoor|Allow user to lock trapdoors.
    lockette.user.create.doorUser|Allow user to lock doors.
    lockette.admin.create.chest|Allow admins to create locked containers for other users.
    lockette.admin.create.furnace|Allow admins to create locked containers for other users.
    lockette.admin.create.dispenser|Allow admins to create locked containers for other users.
    lockette.admin.create.trapdoor|Allow admins to create locked containers for other users.
    lockette.admin.create.door|Allow admins to create locked containers for other users.
    lockette.admin.break|Allow admins to break protected containers
    lockette.admin.reload|`/lockette reload`
    lockette.admin.bypass|Allow admins to open protected doors
    lockette.admin.snoop|Allow admins to open protected containers

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

---

## Configuration

The main configuration file for Lockette can be found in: `/plugins/Lockette/config.yml`

### Config Options

---
**`enable-protection-doors`**  
:   Enables support for private doors, defaults to `true`.  
    Example: `enable-protection-doors: true`

---
**`broadcast-break-target`**  
:   Sets the Group or Player that broadcast messages are sent to. The default value is `'[Everyone]'`.

    Values|Notes
    -|-
    `'[Everyone]'` | Broadcasts the message to everyone.
    `'[Operators]'`| Broadcasts the message to server Ops.  
    `'[Group]'`| Broadcasts the message to a specific group (ex: Admin).  
    `'Player'` | Broadcasts the message to a specific user (ex: Notch).  
    `''`           | Don't broadcast anything.

    *A supported permissions plugin must be installed in order to use the `'[Group]'` value.*

    Example:  
    : `broadcast-break-target: 'Notch'` - Notify Notch  
       `broadcast-break-target: '[Admin]'` - Notify the Admin group

---
**`enable-protection-trapdoors`**  
:   Enables support for trapdoors, defaults to `true`.  
    Example: `enable-protection-trapdoors: true`

---
**`enable-permissions`**  
:   Enables the use of permission nodes, defaults to `false`.

    Values|Notes
    -|-
    `true` | Use permissions nodes to grant access.
    `false`| All non Ops are able to create protected containers. Ops can break protected chests, look inside the chest (if `allow-admin-snoop` is set to true) & reload the plugin.

    Example: `enable-permissions: true`

---
**`enable-messages-owner`**  
:   Enables or disables groups of messages listed in the strings.yml file. Not counting the broadcast ones, defaults to `false`.  
    Example: `enable-messages-owner: true`

---
**`allow-admin-bypass`**  
:   Allows admins to go through protected doors, defaults to `true`.  
    Example: `allow-admin-bypass: false`

---
**`allow-admin-snoop`**  
:   Allows admins open protected chests, defaults to `false`.  
    Example: `allow-admin-snoop: true`

---
**`broadcast-reload-target`**  
:   Sets the Group or Player that broadcast messages are sent to when `/lockette reload` is performed. The default value is `'[Operators]'`.

    Values|Notes
    -|-
    `'[Everyone]'` | Broadcasts the message to everyone.
    `'[Operators]'`| Broadcasts the message to server Ops.  
    `'[Group]'`| Broadcasts the message to a specific group (ex: Admin).  
    `'Player'` | Broadcasts the message to a specific user (ex: Notch).  
    `''`           | Don't broadcast anything.

    *A supported permissions plugin must be installed in order to use the `'[Group]'` value.*

    Example: `broadcast-reload-target: '[Admin]'` - Notify the Admin group

---
**`enable-messages-help`**  
:   Enables or disables the help messages, defaults to `true`.  
    Example: `enable-messages-help: true`

---
**`default-door-timer`**  
:   Sets the door closing timer for all protected doors on the server, unless overridden by a specific sign. Defaults to `0`, which disables the door closing timer.  
    Example: `default-door-timer: 2`

---
**`broadcast-snoop-target`**  
:   Sets the Group or Player that broadcast messages are sent to. The default value is `'[Everyone]'`.

    Values|Notes
    -|-
    `'[Everyone]'` | Broadcasts the message to everyone.
    `'[Operators]'`| Broadcasts the message to server Ops.  
    `'[Group]'`| Broadcasts the message to a specific group (ex: Admin).  
    `'Player'` | Broadcasts the message to a specific user (ex: Notch).  
    `''`           | Don't broadcast anything.

    *A supported permissions plugin must be installed in order to use the `'[Group]'` value.*

    Example: `broadcast-snoop-target: '[Everyone]'` - Notify everyone on the server.

---
**`explosion-protection-all`**  
:   Enabling this extends explosion protection to all containers on the server, not just [Private] ones. Default is set to `false`.  
    Example: `explosion-protection-all: false`

---
**`enable-messages-admin`**  
:   Enables or disables the admin messages listed in the strings.yml file. Not counting the broadcast ones, defaults to `true`.  
    Example: `enable-messages-admin: true`

---
**`strings-file-name`**  
:   File that holds the plugin strings, defaults to `strings.yml`.  
    Example: `strings-file-name: strings.yml`

---
**`enable-quick-protect`**  
:   Protect containers instantly by right clicking on them while holding a sign, defaults to `true`.  
    Example: `enable-quick-protect: true`

---

**`enable-messages-error`**  
:   Enables or disables the error messages in strings.yml, defaults to `true`.  
    Example: `enable-quick-protect: true`

---
**`enable-messages-user`**  
:   Enables or disables the user messages in strings.yml, defaults to `true`.  
    Example: `enable-quick-protect: true`

---




### Language Options
Use `strings.yml` to adjust the default Lockette messages. Only modify the portion after the colon ":". The example below highlights the portion you can modify. Color tags are sadly not supported in version 1.4.

`msg-user-resize-owned: {==You cannot resize a chest claimed by ***.==}`

#### Default strings
```
alternate-private-tag: Private
alternate-moreusers-tag: More Users
alternate-everyone-tag: Everyone
alternate-operators-tag: Operators
alternate-timer-tag: Timer
msg-user-conflict-door: Conflicting door removed!
msg-user-illegal: Illegal chest removed!
msg-user-resize-owned: You cannot resize a chest claimed by ***.
msg-help-chest: Place a sign headed [Private] next to a chest to lock it.
msg-owner-release: You have released a container!
msg-admin-release: (Admin) @@@ has broken open a container owned by ***!
msg-user-release-owned: You cannot release a container claimed by ***.
msg-owner-remove: You have removed users from a container!
msg-user-remove-owned: You cannot remove users from a container claimed by ***.
msg-user-break-owned: You cannot break a container claimed by ***.
msg-user-denied-door: You don't have permission to use this door.
msg-user-touch-owned: This container has been claimed by ***.
msg-help-select: Sign selected, use /lockette <line number> <text> to edit.
msg-admin-bypass: Bypassed a door owned by ***, be sure to close it behind you.
msg-admin-snoop: (Admin) @@@ has snooped around in a container owned by ***!
msg-user-denied: You don't have permission to open this container.
msg-error-permission: Permission to lock container denied.
msg-error-claim: No unclaimed container nearby to make Private!
msg-error-claim-conflict: Conflict with an existing protected door.
msg-admin-claim-error: Player *** is not online, be sure you have the correct name.
msg-admin-claim: You have claimed a container for ***.
msg-owner-claim: You have claimed a container!
msg-error-adduser-owned: You cannot add users to a container claimed by ***.
msg-error-adduser: No claimed container nearby to add users to!
msg-owner-adduser: You have added users to a container!
msg-help-command1: /lockette <line number> <text> - Edits signs on locked containers. Right click on the sign to edit.
msg-help-command2: /lockette fix - Fixes an automatic door that is in the wrong position. Look at the door to edit.
msg-help-command3: /lockette reload - Reloads the configuration files.  Operators only.
msg-help-command4: /lockette version - Reports Lockette version string.
msg-admin-reload: Reloading plugin configuration files.
msg-error-fix: No owned door found.
msg-error-edit: First select a sign by right clicking it.
msg-owner-edit: Sign edited successfully.
```