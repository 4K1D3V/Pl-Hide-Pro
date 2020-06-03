```#
#
#Note that this is the Bungeecord configuration and therefore some spigot function are missing
#
#For some commands, the tabblock function may not work with subargs.
#This is because these commands from the bukkit server are themselves.
#In this case, you can simply install the plugin on the subserver and set it there.
#


#Message if you type a blocked command | Enter none to disable
blocked-command-message: "&7Unknown command"

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass will see the real plugins
/pl-message: 'Plugins (0):'

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

#Blocks all "/<pluginname>:<command>" from tabcompleting and from executing
block-plugin-named-commands: true

#If you want to use "plugin:<pluginName> make sure you installed PL-Hide-Pro on the MC-Servers and enabled bungee-mode
#Also "plugin:<pluginName> won't work with bungeecord plugins

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
    #Minecraft server names on which this group will be applied | all means on every server.
    #type /servers in Bungeecord to find out which servernames are available
    servers:
      - all
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
    servers:
      - example1
    priority: 1
    included-groups:
      - none


#Don't change
version: "1.2"
```