```
#
#Note that this is the Bungeecord configuration and therefore some spigot function are missing
#

#Config version. Don't change!
version: "7"

debug: false

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass will see the real plugins
/pl-message: 'Plugins (0):'

#Changes the server brand in the upper left of the f3 debug screen
#Use %server% to display the server name of the mc server.
f3-server-brand: '&3Plugin&7-&3Hide&7-&6Pro'
replace-f3-server-brand: true

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

#If you want to use the feature "plugin:<pluginName> make sure you installed PL-Hide-Pro on the MC-Servers and enabled bungee-mode
#Also "plugin:<pluginName> won't work with bungeecord plugins
#If you change these value, the server has to be restarted
bungee-mode: false
ip: 127.0.0.1
port: 1550

#Blocks all "/<pluginname>:<command>"
block-plugin-named-commands-tabcomplete: true
block-plugin-named-commands-execution: true


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
      #bungeecord commands
      - perms
      - bungee
      - glist
      - server
    #If the value is  blacklist, the commands in the "commands" list are blocked
    #If the value is  whitelist, the commands in the "commands" list are only executable
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
      - perms
      - bungee
      - glist
      - server
    #If the value is blacklist, the commands in the "tabcomplete" list are removed from the tab complete
    #If the value is whitelist, the commands in the "tabcomplete" list are only visible in the tab complete
    group-mode-tabcomplete: blacklist
    #If a player is in two groups, the group with the higher priority number is used
    #The minimum value is 0
    priority: 0
    #Message if you type a blocked command | Enter none to disable
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    #Minecraft server names on which this group will be applied | all means on every server.
    #type /servers in Bungeecord to find out which servernames are available
    servers:
      - all
    #here you can add other groups
    #The group mode is taken from the main group, in this case the main group is "default"
    included-groups:
      - Test

  #This group for example will remove and block all commands for the server lobby
  #add permission plhide.group.test to apply the group "Test"
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

```