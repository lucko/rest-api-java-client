# LuckPerms REST API - Java Client

The [LuckPerms REST API](https://github.com/LuckPerms/rest-api) allows developers to query LuckPerms data using HTTP calls.

This library allows developers to make these HTTP calls easily using a familiar Java API. :)

### Usage

Add a dependency to your Maven/Gradle buildscript:

e.g.

```groovy
repositories {
    maven {
        url 'https://oss.sonatype.org/content/repositories/snapshots'
    }
}

dependencies {
    implementation 'net.luckperms:rest-api-java-client:0.1-SNAPSHOT'
}
```

```xml
<repositories>
    <repository>
        <id>sonatype-snapshots</id>
        <url>https://oss.sonatype.org/content/repositories/snapshots</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>net.luckperms</groupId>
        <artifactId>rest-api-java-client</artifactId>
        <version>0.1-SNAPSHOT</version>
    </dependency>
</dependencies>
```

Then, create a new client and start making calls:

```java
LuckPermsRestClient client = LuckPermsRestClient.builder()
        .baseUrl("http://localhost:8080")
        .apiKey("abc123")
        .build();
        
Response<Group> response = client.groups().get("admin").execute();
```
