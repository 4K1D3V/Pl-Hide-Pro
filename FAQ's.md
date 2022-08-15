## **How to give access to another/multiple groups?**


You'll need to assign every group under "inherited-groups:". Meaning if you have ranks e.g.Admin, Moderator and Default, this is how you'd assign 2 groups to the group Admin:
```  
  Admin:
    commands:
      - ban
    tabcomplete:
      - ban
    priority: 20
    inherited-groups:
      - default
      - Moderator
```
**Note that groups are inherited recursively**. For example, if moderator also inherits default, you don't have to inherit default for the Admin group as well. 



## **How do my players get pl-hide group permissions?**


By default everyone gets the group "default" regardless of whether you assign it or not. Otherwise, you need to add the permission for example "**plhide.group.test**" to apply the group "Test". Be sure to not get confused with "pl-hide.group.test" as this could lead to failure.


## **What is a ```group mode```?**

If a group should block commands and remove these commands from the tab completion, set group-mode to blacklist.

Otherwise if group-mode is set to whitelist, only the listed commands will be executable and all not listed commands will be removed from the tab complete


## **How to set the ```group mode```?**

By default the group mode is whitelist. If you want to change it to blacklist, you have to give the player a permission:
For the commands it's plhide.blacklist.commands and for the tab complete it's plhide.blacklist.tabcomplete
 

## **How to block all subargs of a command in whitelist mode?** 
That's what the "\~" character is for. It blocks everything from the "\~" character.
<br><br>
For example: If you whitelist "help \~" you can only execute "/help" but not "/help 1", same with the tabcompletion. It's also not possible to execute for "/help 1 1"

## **How to allow the base command and some subargs?**

If you want the base command and only some subargs of the command to be executable, then you need the "\~" after the base command:
For example, you have the warp command with the subargs admin, test, player, city
Then if you would like to allow "/warp", "/warp player", and "/warp city" to be executable, you would list it like this:
```
commands:
  - warp ~
  - warp player
  - warp city
```
The same applies to the tabcomplete

## **What is the operator ```*```?**

The * stands for every possible word. You can only use them in subargs, so listing "* test" or "*" won't work
<br>Examples:

Using whitelist mode:
<br>If you list "ban * test" it's allowed to execute `/ban player test` or `/ban Nononitas test` but it's not allowed to execute `/ban Nononitas Hello`. You are also allowed to execute `/ban player test Lol` but you are not allowed to execute `/ban player Lol Hello`

Using blacklist mode:
<br>If you list "ban * test" `/ban player test` is blocked or `/ban Nononitas test` is blocked but not `/ban Nononitas Hello`. The command `/ban player test Lol` is also blocked, but `/ban player Lol Hello` is not

Same for the tab completion

## **Add all commands of a plugin automatically?**

Yes. Just add for example ```- plugin:WorldEdit``` to your list<br>
If you use the Bungeecord version follow this [guide](https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Setup-the-autlisting-command-function-per-plugin-for-Spigot-plugin-commands-in-Bungeecord)


## **Add worldedit commands?**

There's a common misconception that adding ```- /``` will work. It isn't going to work because that isn't a command. Instead use ```- /wand``` as an example.


## **I think my groups are not set correctly**

- Check if the priority is correctly set.
- Check if the servers list is correctly [Bungee/Velocity]
- If you are using the Bungee/Velocity version, check that the permissions are set via a Bungee/Velocity permission manager and are set without context
- If you have * or op you might also be always in the * and/or op group
- Execute /plhide check <playerName> for detailed information (might /plhide-bungee or /plhide-velocity depending where you installed plhide)

## **Create a bypass group**

If you want to create a group where neither commands nor tab complete is blocked, create a group as shown below
```  
  Bypass:
    commands: []
    tabcomplete: []
    priority: 20 
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    inherited-groups: []
```
Now give the user the permissions plhide.group.bypass, plhide.blacklist.* and plhide.unblock-plugin-named-commands.*

## **Tab completion with a space**
If you have a tab completion where you can tab `command arg` as one entry, you cannot list the entry the default way. Instead you need to list it like `commands%space%arg`