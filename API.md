
## For intense help open a Discord ticket. This is just a small overview with very little explanation


### Include API 


```xml
<repository>
    <id>nononitas-public</id>
    <url>https://repo.nononitas.eu:443/artifactory/nononitas-public</url>
</repository>

<dependency>
    <groupId>eu.nononitas</groupId>
    <artifactId>pl-hide-pro-api</artifactId>
    <version>NEWEST-VERSION</version>
    <scope>provided</scope>
</dependency>
```

### Events

* SetGroupEvent
* PlayerExecuteCommandEvent

### Make a listener

Replace Event with a valid Event

```java
    @Listener
    public void onEvent(Event event){
        
    }
```

### Register a listener

`PlHideAPI.getEventManager().registerListener(new Listener());`

### Get a PlHidePlayer

`PlHideAPI.getPlayerManager().getPlHidePlayer(player);`

