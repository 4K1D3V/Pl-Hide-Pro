```
#
#Note that this is the Bungeecord configuration and therefore some spigot function are missing
#Wiki: https://github.com/Nononitas/Plugin-Hide-Pro/wiki
#

#Config version. Don't change!
version: 10

debug: false

#Message shown if you type /pl | Enter none to disable | Players with the permission plhide.bypass.pl-message.pl will see the real plugins when executing /plugins
/pl-message: 'Plugins (0):'

#Changes the server brand in the upper left of the f3 debug screen
#Use %server% to display the server name of the mc server.
f3-server-brand: '&3Plugin&7-&3Hide&7-&6Pro'
replace-f3-server-brand: true

#Stay on the newest version to get better features!
#Enable or disable automatic ingame update notification on join
update-notify: true

#If you want to use the feature "plugin:<pluginName> make sure you installed Pl-Hide-Pro on the MC-Servers and enabled bungee-mode
#Read here for more details https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Setup-the-autlisting-command-function-per-plugin-for-Spigot-plugin-commands-in-Bungeecord
bungee-mode: false
#Only change this ip if you know what you are doing. If you are using a vserver (not a gameserver) you might be able to use 127.0.0.1 instead
ip: 0.0.0.0
#If the ip is other than 127.0.0.1, make sure the port is open
#Do NOT change the port unless you are 100% sure what you are doing. In most cases it is recommended to leave the default value
port: 1550


groups:
  #If no group is set via the permission plhide.group.<group> this will be used
  #Do not rename the default group!
  default:
    servers:
      fallback:
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
    #Minecraft's servers on which the group will be enabled | all means on every server.
    #type /servers in Bungeecord to find out which servernames are available
    #Regex is supported
    enabled_servers:
      - all
    #Here you can add other groups: The commands and tab completion from the "inherited groups" will be added to this group
    #Read more here https://github.com/Nononitas/Plugin-Hide-Pro/wiki/Group#inheritance
    #The group modes are taken from the parent group, in this case the parent group is "default"
    #The group is only inherited if a server in the "servers" list of the subordinate group matches the player's server
    inherited-groups:
      - example

  #Give the player the plhide.group.example permission to use the group
  example:
    servers:
      #If no matching server could be found (for example creative) this key will be used.
      fallback:
        commands: [ ]
        tabcomplete: [ ]
      #Commands listed here will be added to servers where the name starts with "Lobby-" (for example "Lobby-1", "Lobby-230")
      "Lobby-.*":
        commands: [ ]
        tabcomplete: [ ]
      #Commands listed here will only be added to the server with the name "Survival"
      Survival:
        commands: [ ]
        tabcomplete: [ ]
      #Commands listed here will be added to every other server automatically. This key (all) is optionally
      all:
        commands: [ ]
        tabcomplete: [ ]
      #Option for which servers the group should be enabled
    enabled_servers:
      - all
    priority: 1
    blocked-command-message: "Unknown command. Type \"/help\" for help."
    inherited-groups: [ ]

  #This group will be added AUTOMATICALLY if you have * permissions
  #Leave it commented out to keep it disabled
#  "*":
#    servers:
#      fallback:
#        commands: []
#        tabcomplete: []
#    enabled_servers:
#      - all
#    priority: 10
#    blocked-command-message: "Unknown command. Type \"/help\" for help."
#    inherited-groups: []
```