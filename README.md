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

### Mybatis via Spring
```
<bean id="SomeId" class="org.mybatis.spring.SqlSessionFactoryBean">
    <!-- your configuration -->
    <property name="typeHandlersPackage" value="com.github.javaplugs.mybatis" />
</bean>
```