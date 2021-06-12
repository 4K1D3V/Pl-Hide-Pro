### Q: **How do I give a group access to another/multiple groups?**


A: You'll need to assign every group under "included-groups:". Meaning if you have ranks e.g.Admin, Moderator and Default, this is how you'd assign 2 groups to the group Admin:
```  
  Admin:
    commands:
      - ban
    group-mode-commands: whitelist
    tabcomplete:
      - ban
    group-mode-tabcomplete: whitelist
    priority: 20
    included-groups:
      - default
      - Moderator
```
**Note that groups are inherited recursively**. For example, if moderator also includes default, you don't have to inherit default for the Admin group as well.

***

### Q: **How do my players get pl-hide group permissions?**


A: By default everyone gets the group "default" regardless of whether you assign it or not. Otherwise, you need to add the permission for example "**plhide.group.test**" to apply the group "Test". Be sure to not get confused with "pl-hide.group.test" as this could lead to failure.

***

### Q: **What is a ```group mode```?**

A:If a group should block commands and remove these commands from the tab completion, set group-mode to blacklist.

Otherwise if group-mode is set to whitelist, only the listed commands will be executable and all not listed commands will be removed from the tabcomplete

***

### Q:**What is the operator ```~```?**

A:The operator ~ only works with whitelists
Examples:

If you list "help ~" in the command list, /help can only be executed without its subarguments, "/ help ?" can't be executed.

If you list "help ~" in the "tabcomplete" list, /help is displayed without its subarguments, "/ help ?" will not be visible.

***

### Q: **Can I add all commands of a plugin?**

A: Yes. Just add for example ```- plugin:WorldEdit``` to your list
If you use Bungeecord follow this [guide](https://github.com/Nononitas/Plugin-Hide-Pro/wiki/FAQ's#q-can-i-add-all-commands-of-a-plugin)

***

### Q: **My groups aren't being set correctly, how do I check what permission group has what plhide group?**

A: Use the ```debug: true``` section in the config.yml. Reload the plugin so it will show you where each group is being set. The debug log is located in the plhide folder.

***

### Q: **How do i add worldedit commands?**

A: There's a common misconception that adding ```- /``` will work. It isn't going to work because that isn't a command. Instead use ```- /wand``` as an example.
