```
#
#Note that this is the Velocity configuration and therefore some spigot/bungee version functions are missing
#Wiki: https://github.com/Nononitas/Plugin-Hide-Pro/wiki
#

#Config version. Don't change!
version: 4

debug: false

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass.pl-message will see the real plugins
/pl-message: 'Plugins (0):'

#Changes the server brand in the upper left of the f3 debug screen
#Use %server% to display the server name of the mc server.
f3-server-brand: '&3Plugin&7-&3Hide&7-&6Pro'
replace-f3-server-brand: true

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

groups:
  #If no group is set via the permission plhide.group.<group> this will be used
  #Do not rename the default group!
  default:
    #The list of commands whose execution will be allowed only
    commands:
      - spawn
      - tpa
      - tpaccept
      - tpdeny
      - pay
      - money
      - balance
      - warp
      - msg
      - r
    #The list of commands that will be made visible only in tabcomplete
    tabcomplete:
      - spawn
      - tpa
      - tpaccept
      - tpdeny
      - pay
      - money
      - balance
      - warp
      - msg
      - r
    #If a player is in two groups, the group with the higher priority number is used
    #The minimum value is 0
    priority: 0
    #The message if you type a blocked command | Enter none to disable | %player% will be replaced with the playername
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    #Minecraft server names on which this group will be applied | all means on every server.
    #type /servers in Bungeecord to find out which servernames are available
    servers:
      - all
    #Here you can add other groups: The commands and tab completion from the "inherited groups" will be added to this group
    #Read more here https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Group#inheritance
    #The group modes are taken from the parent group, in this case the parent group is "default"
    #The group is only inherited if a server in the "servers" list of the subordinate group matches the player's server
    inherited-groups:
      - Test

  #This group will remove all commands from the tab complete and block them from being executed
  #Give the player the plhide.group.test permission to use the group
  Test:
    commands: [ ]
    tabcomplete: [ ]
    servers:
      - lobby
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    inherited-groups: [ ]

  #This group will be added AUTOMATICALLY if you have * permissions
  #Leave it commented out to keep it disabled
#  "*":
#    commands: []
#    tabcomplete: []
#    servers:
#      - all
#    priority: 10
#    blocked-command-message: "Unknown command. Type \"/help\" for help."
#    inherited-groups: []
```