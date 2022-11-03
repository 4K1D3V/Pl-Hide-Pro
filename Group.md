## Groupname

Each group needs a different **groupname**.

To add a specific group to a user, add the permission **plhide.group.{groupname}**. If a player has **2 groups** permissions, then the group is set depending on the **priority** (the higher the number, the higher the priority). If they have the same priority booth groups will be applied (they get merged)
With the Bungeecord/Velocity plugin you can also choose on which servers the groups should be used.

## Commands

The "**commands**" **section** lists the commands that can either be blocked or executed exclusively. Listing subcommads is also possible:

Example1 (**blacklist**): If you list "cmd test" it will block "cmd test" and its subargs ("cmd test <args>"), but it will not block "cmd" or "cmd help"

Example2 (**whitelist**): If you list "cmd test" it will block "cmd" and "cmd help", but it will not block "cmd test" or "cmd test <args>".

## Tabcomplete

The "**tabcomplete**" section lists the commands that are either be removed or only visible in the tabcompletion. List subtabcompletions is also possible:


Example1 (**blacklist**): If you list "cmd test" it will remove the subarg "test" and its subargs but not "cmd" itself. So "cmd help" will be visible.


Example2 (**whitelist**): If you list "cmd test" it will remove all subargs except "test" and its subargs but not "cmd" itself. So "cmd help" not be visible

## Groupmode

The group mode decides whether the list is a blacklist or whitelist. By **default** the group mode is **whitelist**. If you want to change it to blacklist, you have to give the player a permission:
For the commands it's **plhide.blacklist.commands** and for the tabcomplete it's **plhide.blacklist.tabcomplete**

## Enabled Servers

If you are using the Bungeecord/Velocity plugin, there is another list called **enabled_servers**. Here you add the server names on which the group is enabled.
The default value is "all".
Regex is also supported.

## Servers
This option is only available if using the Bungeecord/Velocity version<br>
Here you can add server names to have different commands/tabcomplete on different servers<br>

```
  example:
    servers:
      #If no matching server could be found (for example creative) this key will be used.
      fallback:
        commands: [ ]
        tabcomplete: [ ]
      #Commands listed here will be added to servers where the name starts with "Lobby-" (for example "Lobby-1", "Lobby-230")
      "Lobby-.*":
        commands: [ ]
        tabcomplete: [ ]
      #Commands listed here will only be added to the server with the name "Survival"
      Survival:
        commands: [ ]
        tabcomplete: [ ]
      #Commands listed here will be added to every other server automatically. This key (all) is optionally
      all:
        commands: [ ]
        tabcomplete: [ ]
      #Option for which servers the group should be enabled
    enabled_servers:
      - all
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    inherited-groups: [ ]
```

## Inheritance

In the "**inherited-groups**" section you can add other groups.
The commands and tab completion from the "inherited groups" will be added to this group. Note that the implemented groups **implement their implemented groups**!​
So the inheritance is recursive means: if you have, for example, 3 groups: Default, Moderator, Admin. Moderator inherits from Default and Admin inherits from Moderator, then Admin also inherits the Default group, since Moderator inherits it 

## Group merging

A player can also have multiple parent groups at the same time:
If two or more groups have the same priority and the player has permission for them, all groups for which the player has permission will be applied