```#OP-protection: Player can only be op'ed if they are in the "allowed-operators" list
op-protection: false
allowed-operators:
 - Player1
 - Player2
#If you try to Op someone who isn't in the list
op-message: "&cThe Player isn't a listed operator!!!"
#Players who are operators and are not in the list can't connect and will be deop'ed.
unauthorized-operator-kick-message: '&cYou are not allowed to be an operator'

#Message if you type a blocked command | Enter none to disable
blocked-command-message: "&7Unknown command"

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass will see the real plugins
/pl-message: 'Plugins (0):'

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

groups:
 #If no group is set via the permission plhide.group.<group> this will be applied
  #Do not rename the default group!
  default:
 #The list of commands whose execution will be blocked or only executable
    commands:
     - ver
      - version
      - about
      - bukkit
      - icanhasbukkit
      - help
      - '?'
      - me
      - minecraft:me
      - minecraft:help
      - bukkit:?
      - bukkit:help
      - plugins
      - pl
      - bukkit:pl
      - bukkit:plugins
      - bukkit:ver
      - bukkit:version
      - bukkit:about
      #The plugin commands
      - pl-hide-pro:plhide
      - plhide
    #If true, the commands in the "commands" list are blocked
    #If false, the commands in the "commands" list are only executable
    should-list-block1: true
  #The list of commands that will be removed from the tabcomplete or only visible
    tabcomplete:
     - ver
      - version
      - about
      - bukkit
      - icanhasbukkit
      - help
      - '?'
      - me
      - minecraft:me
      - minecraft:help
      - bukkit:?
      - bukkit:help
      - plugins
      - pl
      - bukkit:pl
      - bukkit:plugins
      - bukkit:ver
      - bukkit:version
      - bukkit:about
      #The plugin commands
      - pl-hide-pro:plhide
      - plhide
    #If true, the commands in the "tabcomplete" list are removed from the tab complete
    #If false, the commands in the "tabcomplete" list are only visible in the tab complete
    should-list-block2: true
    #If a player is in two groups, the group with the higher priority number is used
    #The minimum value is 0
    priority: 0
    #here you can add other groups
    #The group type(should-list-block) is taken from the main group, in this case the main group is "default"
    included-groups:
     - Test

  #add permission plhide.group.test to apply the group "Test"
  Test:
    commands:
     - none
    should-list-block1: true
    tabcomplete:
     - none
    should-list-block2: true
    priority: 1
    included-groups:
     - none


#Don't change
version: "1.2"
```