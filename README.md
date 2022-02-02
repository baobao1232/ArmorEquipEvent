# ArmorEquipEvent

This is a maintained version of [Arnuh's ArmorEquipEvent](https://github.com/Arnuh/ArmorEquipEvent) including a proper maven artifact.

## Maven information

The latest version is available in my maven repository:

```xml
<repository>
  <id>jeff-media-public</id>
  <url>https://hub.jeff-media.com/nexus/repository/jeff-media-public/</url>
</repository>

<dependency>
  <groupId>com.jeff_media</groupId>
  <artifactId>ArmorEquipEvent</artifactId>
  <version>1.0.0</version>
  <scope>compile</scope>
</dependency>
```

Please note that you must also shade and relocate the artifact:

```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-shade-plugin</artifactId>
      <version>3.2.4</version>
      <configuration>
        <relocations>
          <relocation>
            <pattern>com.jeff_media.armorequipevent</pattern>
            <shadedPattern>YOUR.PACKAGE.NAME.armorequipevent</shadedPattern>
          </relocation>
        </relocations>
      </configuration>
      <executions>
        <execution>
          <phase>package</phase>
          <goals>
            <goal>shade</goal>
          </goals>
        </execution>
      </executions>
    </plugin>
  </plugins>
</build>
```

## Usage

To use the ArmorEquipEvent, you first have to register the Listener, for example in your onEnable() method:

```java
import com.jeff_media.armorequipevent.ArmorEquipEvent;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        ArmorEquipEvent.registerListener(this);
    }
    
}
```

You can now listen to this event, cancel it or change the equipped armor.

## Javadocs

Javadocs are available here: https://hub.jeff-media.com/javadocs/armorequipevent

## Other libraries by me

### [CustomBlockData](https://github.com/JEFF-Media-GbR/CustomBlockData)
My **CustomBlockData** library provides a PersistentDataContainer for every block in your world - easily save EVERY information you like inside blocks, without any external storage needed!

### [MorePersistentDataTypes](https://github.com/JEFF-Media-GbR/MorePersistentDataTypes)
Adds a ton of new **PersistentDataTypes** to use with Bukkit's PersistentDataContainer.

### [SpigotUpdateChecker](https://github.com/JEFF-Media-GbR/Spigot-UpdateChecker)
Powerful **UpdateChecker** for your plugins, with only **one line of code**.

## Discord

If you need help, feel free to join my Discord server and head to #programming-help:

<a href="https://discord.jeff-media.com"><img src="https://api.jeff-media.de/img/discord1.png"></a>

## Donate

If you are using this project in your paid plugins, or if you just want to buy me a coffee, I would be happy over a small donation :)

<a href="https://paypal.me/mfnalex"><img src="https://www.paypalobjects.com/en_US/DK/i/btn/btn_donateCC_LG.gif" border="0" name="submit" title="PayPal - The safer, easier way to pay online!" alt="Donate with PayPal" /></a>
