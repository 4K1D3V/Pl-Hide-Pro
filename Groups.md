Each group has a **command list** and a **tab-complete** list
There are two types of groups:<br/>
**Blacklist**-> Blocks commands or removes commands from tabcomplete<br/>
**Whitelist**-> allows commands or displays commands in tabcomplete<br/>
A group **can inherit** from other groups. These then assume the group type of the parent group
To add a specific group to a user, add the permission **plhide.group.{groupname}**. If a player has **2 groups** permissions, then the group is set depending on the **priority** (the higher the number, the higher the priority)
With the Bungeecord plugin you can choose on which servers the groups should be applied.