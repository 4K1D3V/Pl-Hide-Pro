* Enable the bungee-mode in the Bungee config.yml of my plugin
  * If the Bungeecord server and the Spigot server are on the same machine, so they have the same IP, leave the IP at 127.0.0.1
  * If they have different IPs, enter those from the Bungeecord server 
* Reload PLHide-Pro with /plhide-bungee rl
* Install PL-Hide-Pro on each subserver
* Copy the secret.key from the PL-Hide-Pro folder on the Bungeeplugin into each PL-Hide-Pro folder on the sub-servers
* Enable the bungee-mode in the Spigot config.yml of my plugin
  * If the Bungeecord server and the Spigot server are on the same machine, so they have the same IP, leave the IP at 127.0.0.1
  * If they have different IPs, enter those from the **Bungeecord** server 
* Reload PLHide-Pro with /plhide rl

Now `plugin:<pluginName>` should work for all Spigot plugins in Bungee config.yml of my plugin
