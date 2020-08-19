```
#
debug: false

#OP-protection: Player can only be op'ed if they are in the "allowed-operators" list
op-protection: false
allowed-operators:
  - Player1
  - Player2
#If you try to Op someone who isn't in the list
op-message: "&cThe Player isn't a listed operator!!!"
#Players who are operators and are not in the list can't connect and will be deop'ed.
unauthorized-operator-kick-message: '&cYou are not allowed to be an operator'


#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass will see the real plugins
/pl-message: 'Plugins (0):'

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

#Blocks all "/<pluginname>:<command>"
block-plugin-named-commands-tabcomplete: true
block-plugin-named-commands-execution: true

#Set true if you are using the bungeecord version and want to block commands via plugin:<pluginname>
#If true the groupsystem in this config will be disabled
bungee-mode: false
#If the proxy has a different ip and enter the proxys ip
#Make sure the port is open
#If you change these values, the server has to be restarted
ip: 127.0.0.1
port: 1550

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
    #If the value is blacklist, the commands in the "commands" list are blocked
    #If the value is whitelist, the commands in the "commands" list are only executable
    group-mode-commands: blacklist
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
    #If the value is blacklist, the commands in the "tabcomplete" list are removed from the tab complete
    #If the value is whitelist, the commands in the "tabcomplete" list are only visible in the tab complete
    group-mode-tabcomplete: blacklist
    #If a player is in two groups, the group with the higher priority number is used
    #The minimum value is 0
    priority: 0
    #Message if you type a blocked command | Enter none to disable
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    #here you can add other groups
    #The group mode is taken from the main group, in this case the main group is "default"
    included-groups:
      - none

  #add permission plhide.group.test to apply the group "Test"
  Test:
    commands:
      - none
    group-mode-commands: blacklist
    tabcomplete:
      - none
    group-mode-tabcomplete: blacklist
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    included-groups:
      - none


#Don't change
version: "1.6"
```