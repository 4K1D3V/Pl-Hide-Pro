### **ChatControl**

Make sure you have disabled the tabcomplete blocker in the settings.yml

The path is Packets -> Tab_Complete

There should be an option to disable blocking in case you enabled it.

Example for the free version:

![](https://i.postimg.cc/cJXzfqqS/Chat-Control.png)

***

### **AdminAnything**

Make sure you set this to false in the config 

```
tabcompletedisable:
   enabled: false
```

***

### **MyCommand**

Make sure you register the command:

```
example_command: 
  command: /example
  type: TEXT
  text:
  - '&2Example command'
  register: true # <--- Must be true to be visible in tabcomplete by default
```

***

### **DeluxeMenus**

Make sure you register the command:

See [DeluxeMenus's wiki](https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/gui#register-command)