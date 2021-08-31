```
#
#Wiki https://github.com/Nononitas/Plugin-Hide-Pro/wiki
#

#Config version. Don't change!
version: "9"

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

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass will see the real plugins when executing /plugins
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

#Blocks all "/<pluginname>:<command>" | For example it will remove /essentials:warp but not /warp
block-plugin-named-commands-tabcomplete: true
block-plugin-named-commands-execution: true

groups:
  #If no group is set via the permission plhide.group.<group> this will be used
  #Do not rename the default group!
  default:
    #The list of commands whose execution is blocked or can only be executed
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
    #If the value is set to blacklist, the commands in the "commands" list are blocked from execution
    #If the value is set to whitelist, the commands in the "commands" list are the only ones that can be executed
    group-mode-commands: blacklist
    #The list of commands that will be removed from the tab or just made visible
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
    #If the value is set to blacklist, the commands in the "tabcomplete" list are removed from the tab complete
    #If the value is set to whitelist, the commands in the "tabcomplete" list are only visible in the tab complete
    group-mode-tabcomplete: blacklist
    #If a player is in two groups, the group with the higher priority number is used
    #The minimum value is 0
    priority: 0
    #The message if you type a blocked command | Enter none to disable
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    #Here you can add other groups: The commands and tab completion from the "included groups" will be added to this group
    #Read more here https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Group#inheritance
    #The group modes are taken from the parent group, in this case the parent group is "default"
    included-groups:
      - exampleGroup

  #This group will remove all commands from the tab complete and block them from being executed
  #Give the player the plhide.group.test permission to use the group
  Test:
    commands: []
    group-mode-commands: whitelist
    tabcomplete: []
    group-mode-tabcomplete: whitelist
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    included-groups: []


```