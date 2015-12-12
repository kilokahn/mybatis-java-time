# Java 8 time (JSR 310) support for Mybatis

This artefact provides mybatis handlers for core java.time.\* types:
- java.time.Instant (via java.sql.Timestamp)
- java.time.LocalDate (via java.sql.Date)
- java.time.LocalDateTime (via java.sql.Timestamp)
- java.time.LocalTime (via java.sql.Time)
- java.time.OffsetDateTime (via java.sql.Timestamp)
- java.time.ZonedDateTime (via java.sql.Timestamp)

## Adding to your project

For now this package is available only via https://jitpack.io/

### Gradle dependencies
```
repositories {
  maven {
    url "https://jitpack.io"
  }
}

dependencies {
  compile 'com.github.javaplugs:mybatis-java-time:0.2'
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
  <version>0.2</version>
</dependency>
```

## Configure

### Mybatis config
```
<!-- mybatis-config.xml -->
<typeHandlers>
  <typeHandler handler="org.apache.mybatis.custom.typehandlers.InstantHandler"/>
  <typeHandler handler="org.apache.mybatis.custom.typehandlers.LocalDateHandler"/>
  <typeHandler handler="org.apache.mybatis.custom.typehandlers.LocalDateTimeHandler"/>
  <typeHandler handler="org.apache.mybatis.custom.typehandlers.LocalTimeHandler"/>
  <typeHandler handler="org.apache.mybatis.custom.typehandlers.OffsetDateTimeHandler"/>
  <typeHandler handler="org.apache.mybatis.custom.typehandlers.ZonedDateTimeHandler"/>
</typeHandlers>
```

Or you can use package search

```
<!-- mybatis-config.xml -->
<typeHandlers>
  <package name="org.apache.mybatis.custom.typehandlers"/>
</typeHandlers>
```

### Mybatis via Spring
```
<bean id="SomeId" class="org.mybatis.spring.SqlSessionFactoryBean">
    <!-- your configuration -->
    <property name="typeHandlersPackage" value="org.apache.mybatis.custom.typehandlers" />
</bean>
```