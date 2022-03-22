```
#
#More information about how to setup the plugin can be found in the wiki
# https://github.com/Nononitas/Plugin-Hide-Pro/wiki
#

#Config version. Don't change!
version: 11

debug: false

#OP-protection: Player can only be op'ed if they are in the "allowed-operators" list
op-protection: false
allowed-operators:
  - Player1
  - Player2
#If you try to OP someone who isn't in the list
op-message: "&cThe Player isn't a listed operator!"
#Players who are operators and are not in the list can't connect and will be deop'ed.
unauthorized-operator-kick-message: '&cYou are not allowed to be an operator'

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass.pl-message will see the real plugins when executing /plugins
/pl-message: 'Plugins (0):'

#Changes the server brand in the upper left of the f3 debug screen
f3-server-brand: '&3Plugin&7-&3Hide&7-&6Pro'
replace-f3-server-brand: true

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

#Set true if you are using the bungeecord version and want to block commands via plugin:<pluginname> on the bungee version
#If true the groupsystem in this config will be disabled
bungee-mode: false

#If the proxy has a different ip and enter the proxys ip
ip: 127.0.0.1
#Do NOT change the port unless you are 100% sure what you are doing. In most cases it is recommended to leave the default value
port: 1550

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
    #Here you can add other groups: The commands and tab completion from the "inherited groups" will be added to this group
    #Read more here https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Group#inheritance
    #The group modes are taken from the parent group, in this case the parent group is "default"
    inherited-groups:
      - exampleGroup

  #This group will remove all commands from the tab complete and block them from being executed
  #Give the player the plhide.group.test permission to use the group
  Test:
    commands: []
    tabcomplete: []
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    inherited-groups: []
  #This group will be added AUTOMATICALLY if you are an operator
  #Leave it commented out to keep it disabled
#  op:
#    commands: []
#    tabcomplete: []
#    priority: 10
#    blocked-command-message: "Unknown command. Type \"/help\" for help."
#    inherited-groups: []
  #This group will be added AUTOMATICALLY if you have * permissions
  #Leave it commented out to keep it disabled
#  "*":
#    commands: []
#    tabcomplete: []
#    priority: 11
#    blocked-command-message: "Unknown command. Type \"/help\" for help."
#    inherited-groups: []

```