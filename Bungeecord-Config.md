```
#
#Note that this is the Bungeecord configuration and therefore some spigot function are missing
#Wiki: https://github.com/Nononitas/Plugin-Hide-Pro/wiki
#

#Config version. Don't change!
version: "7"

debug: false

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass will see the real plugins when executing /plugins
/pl-message: 'Plugins (0):'

#Changes the server brand in the upper left of the f3 debug screen
#Use %server% to display the server name of the mc server.
f3-server-brand: '&3Plugin&7-&3Hide&7-&6Pro'
replace-f3-server-brand: true

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

#If you want to use the feature "plugin:<pluginName> make sure you installed PL-Hide-Pro on the MC-Servers and enabled bungee-mode
#Read here for more details https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Setup-the-autlisting-command-function-per-plugin-for-Spigot-plugin-commands-in-Bungeecord
bungee-mode: false
#Only change this ip if the Spigot Subservers are hosted on a different ip than the Bungeecord server
ip: 127.0.0.1
#If the ip is other than 127.0.0.1, make sure the port is open
#Do NOT change the port unless you are 100% sure what you are doing. In most cases it is recommended to leave the default value
port: 1550

#Blocks all "/<pluginname>:<command>" | For example it will remove /essentials:warp but not /warp
block-plugin-named-commands-tabcomplete: true
block-plugin-named-commands-execution: true


groups:
  #If no group is set via the permission plhide.group.<group> this will be used
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
      #bungeecord commands
      - perms
      - bungee
      - glist
      - server
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
      - perms
      - bungee
      - glist
      - server
    #If the value is set to blacklist, the commands in the "tabcomplete" list are removed from the tab complete
    #If the value is set to whitelist, the commands in the "tabcomplete" list are only visible in the tab complete
    group-mode-tabcomplete: blacklist
    #If a player is in two groups, the group with the higher priority number is used
    #The minimum value is 0
    priority: 0
    #The message if you type a blocked command | Enter none to disable
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    #Minecraft server names on which this group will be applied | all means on every server.
    #type /servers in Bungeecord to find out which servernames are available
    servers:
      - all
    #Here you can add other groups: The commands and tab completion from the "included groups" will be added to this group
    #Read more here https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Group#inheritance
    #The group modes are taken from the parent group, in this case the parent group is "default"
    #The group is only inherited if a server in the "servers" list of the subordinate group matches the player's server
    included-groups:
      - Test

  #This group will remove all commands from the tab complete and block them from being executed
  #Give the player the plhide.group.test permission to use the group
  Test:
    commands: [ ]
    group-mode-commands: whitelist
    tabcomplete: [ ]
    group-mode-tabcomplete: whitelist
    servers:
      - lobby
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    included-groups: [ ]
  #This group will be added automatically if you have * permissions
  #Do not rename or delete this group
  "*":
    commands: [ ]
    group-mode-commands: blacklist
    tabcomplete: [ ]
    group-mode-tabcomplete: blacklist
    servers:
      - all
    priority: 10
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    included-groups: [ ]

```