[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Specter-green.svg?style=true)](https://android-arsenal.com/details/1/3937) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.bloder/specterlib/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.github.bloder/specterlib)

# Specter

![alt tag](http://orig09.deviantart.net/b7f1/f/2013/300/6/5/one_eyed_spectre_animation_by_lissathekitty-d6rmh63.png)

#### Specter is an easy way to convert a payload data to pojo class.

# How does it work?

Well, to tranfer any data to your pojo classes, you need to add some annotations in payload and pojo classes with the same name.

```java
public class Payload {

  @Specter(name = "name")
  private final String name;
  
  public Payload(String name) {
    this.name = name;
  }
}

public class Pojo {

  @Specter(name = "name")
  public final String name;
  
  public Pojo(String name) {
    this.name = name;
  }
}
```

Then you just need to call specter functions to transfer all payload data to pojo.

```java
Payload payload = new Payload("Daniel");
Pojo pojo = new TestPojo("");

pojo = (Pojo) new Specter()
            .transform(payload)
            .inPojoWithInstance(pojo);
```

That's it!

# Import

### Gradle

```groovy
dependencies {
    compile 'com.github.bloder:specterlib:1.2'
}
```

### Maven

```xml
<dependency>
  <groupId>com.github.bloder</groupId>
  <artifactId>specterlib</artifactId>
  <version>1.2</version>
  <type>pom</type>
</dependency>
```

### Ivy

```xml
<dependency org='com.github.bloder' name='specterlib' rev='1.2'>
  <artifact name='$AID' ext='pom'></artifact>
</dependency>
```
