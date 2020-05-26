##Groups
**Q:**How do I give a group access to another group?
**A:**You'll need to assign every group under "included-groups:". Meaning if you have ranks e.g.Admin, Moderator and Default, this is how you'd assign all 3 groups to the group Admin:
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