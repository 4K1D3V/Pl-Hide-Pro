# Groups
Q: How do I give a group access to another group?<br/><br/>
A: You'll need to assign every group under "included-groups:". Meaning if you have ranks e.g.Admin, Moderator and Default, this is how you'd assign 2 groups to the group Admin:
```  Admin:
    commands:
      - ban
    should-list-block1: false
    tabcomplete:
      - ban
    should-list-block2: false
    priority: 20
    included-groups:
      - default
      - Moderator
```
<br/>
Q: How do my players get pl-hide group permissions?<br/><br/>
A: By default everyone gets the group "default" regardless of whether you assign it or not. Otherwise, you need to add the permission for example **"plhide.group.test"** to apply the group "Test". Be sure to not get confused with "pl-hide.group.test" as this could lead to failure.

# Different servers
Q: How do I give a permission group access to different pl-hide commands across different servers?<br/><br/>
A: You'll need to create different pl-hide groups on the different servers and on the bungeecord server.<br/>Let's say you have a rank "vip" and a creative and survival server. You would need to create 2 different vip groups in the bungeecord server, e.g."vip-Creative" and "vip-Survival", making sure that whatever you put in the bungeecord group, is mirrored across the different servers.<br/>Also if you haven't already realised, you'll need to give the permission group access to both bungee pl-hide groups and for the servers, e.g. "plhide.group.vip-Creative","plhide.group.vip-Survival" and "plhide.group.vip".