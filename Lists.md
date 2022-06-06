## What are lists?

You will find a lists.yml inside the plugin folder. Inside the yml you can create lists like the example below

```
homes:
  - home
  - delhome
  - sethome
```

The advantage is that you don't have to enter the same commands into the groups several times.

You can create as many lists as you like, just add a new one under the old one:

```
homes:
  - home
  - delhome
  - sethome
anotherList:
  - command1
  - command2
```

## How can I use a list?

To use a list write `list:listName` into the commands or tabcomplete list

For example:

```
  groupName:
    commands:
    - help
    - gamemode creative ~
    - gamemode
    - list:homes
    tabcomplete:
    - list:homes
    - gamemode creative ~
    - gamemode
    priority: 0
    blocked-command-message: 'Type "/help" for help.'
    inherited-groups: []
```