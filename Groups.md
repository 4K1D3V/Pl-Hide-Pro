``` groupName:
    commands:
     - command1
      - command2
    should-list-block1: true/false
    tabcomplete:
     - command1
      - command2
    should-list-block2: true/false
    priority: 0
    included-groups:
     - group1
```

Each group needs a different **groupname**.

The "**commands**" **section** lists the commands that can either be blocked or executed exclusively. List subcommads is also possible:
Example1 (**blacklist**): If you list "cmd test" it will block "cmd test" and its subargs ("cmd test <args>"), but it will not block "cmd" or "cmd help"
Example2 (**whitelist**): If you list "cmd test" it will block "cmd" and "cmd help", but it will not block "cmd test" or "cmd test <args>".


The "**tabcomplete**" **section** lists the commands that are either be removed or only visible in the tabcompletion. List subtabcompletions is also possible:
Example1 (**blacklist**): If you list "cmd test" it will remove the subarg "test" and its subargs but not "cmd" itself. So "cmd help" will be visible.
Example2 (**whitelist**): If you list "cmd test" it will remove all subargs except "test" and its subargs but not "cmd" itself. So "cmd help" not be visible


The boolean **should-list block** decides whether the list is a blacklist or whitelist (true=blacklist false=whitelist)

In the "**included-groups**" **section** you can add other groups (The group type of the inherited groups is that of the parent group).
The commands and tabcompletion from the "included groups" will be added to this group. Note that the implemented groups **don't implement their implemented groups**!​