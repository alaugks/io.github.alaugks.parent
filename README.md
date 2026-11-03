# io.github.alaugks:parent

Shared parent POM for io.github.alaugks projects. Provides plugin versions and the profiles `local`, `release` and `test-coverage`.

![Maven Central Version](https://img.shields.io/maven-central/v/io.github.alaugks/parent)

## Usage

```xml
<parent>
    <groupId>io.github.alaugks</groupId>
    <artifactId>parent</artifactId>
    <version>1.0.0</version>
    <relativePath/>
</parent>
```

Spring libraries import the Spring Framework BOM:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-framework-bom</artifactId>
            <version>${spring-framework.version}</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

Child projects still define `name`, `description`, `url` and `scm` themselves.

## Profiles

| Command | Purpose |
|---|---|
| `mvn -U -B deploy -P local` | Deploy to local repository |
| `mvn -U -B deploy -P release` | Deploy to Maven Central |
| `mvn verify -P test-coverage` | JaCoCo report and 90% line coverage check |
