
```xml
<repository>
    <id>nononitas-public</id>
    <url>https://repo.nononitas.eu:443/artifactory/nononitas-public</url>
</repository>

<dependency>
    <groupId>eu.nononitas</groupId>
    <artifactId>Pl-Hide-Pro-API</artifactId>
    <version>1.0</version>
    <scope>provided</scope>
</dependency>
```

### Events

* SetGroupEvent

### Make a listener

Replace Event with a valid Event

```java
    @Listener
    public void onEvent(Event event){
        
    }
```

### Register a listener

`PlHideAPI.getEventManager().registerListener(new Listener());`

### Get A PlHidePlayer

`PlHideAPI.getPlayerManager().getPlHidePlayer(player);`

