# Java 8 time (JSR 310) support for Mybatis 3.x

This artefact provides next java.time.\* types handlers:
- java.time.Instant via java.sql.Timestamp
- java.time.LocalDate via java.sql.Date
- java.time.LocalDateTime via java.sql.Timestamp
- java.time.LocalTime via java.sql.Time
- java.time.OffsetDateTime via java.sql.Timestamp
- java.time.ZonedDateTime via java.sql.Timestamp

## Dependencies 
### Gradle dependencies
```
repositories {
  maven {
    url "https://jitpack.io"
  }
}

dependencies {
  compile 'com.github.javaplugs:mybatis-java-time:0.1'
}
```

### Maven dependencies
```
<repository>
  <id>jitpack.io</id>
  <url>https://jitpack.io</url>
</repository>

<dependency>
  <groupId>com.github.javaplugs</groupId>
  <artifactId>mybatis-java-time</artifactId>
  <version>0.1</version>
</dependency>
```

## Mybatis configuration
```
<!-- mybatis-config.xml -->
<typeHandlers>
  <typeHandler handler="com.github.javaplugs.mybatis.InstantHandler"/>
  <typeHandler handler="com.github.javaplugs.mybatis.LocalDateHandler"/>
  <typeHandler handler="com.github.javaplugs.mybatis.LocalDateTimeHandler"/>
  <typeHandler handler="com.github.javaplugs.mybatis.LocalTimeHandler"/>
  <typeHandler handler="com.github.javaplugs.mybatis.OffsetDateTimeHandler"/>
  <typeHandler handler="com.github.javaplugs.mybatis.ZonedDateTimeHandler"/>
</typeHandlers>
```

Or you can use package search

```
<!-- mybatis-config.xml -->
<typeHandlers>
  <package name="com.github.javaplugs.mybatis"/>
</typeHandlers>
```