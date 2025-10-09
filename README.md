# [Nicks.Guru](https://nicks.guru) Commons Parent

Provides dependencies and build sequence for a typical Spring Boot application:

- **Spring Boot & Spring Cloud** - Core framework and microservices support
- **TestContainers** - Integration testing with containerized databases
- **Camunda BPM** - Business process management and workflow engine
- **AWS SDK** - Amazon Web Services integration
- **Other libraries** - Security, monitoring, caching, and more

## Usage

Pick the most recent version from
[Maven Central](https://central.sonatype.com/namespace/guru.nicks.commons), then use as follows:

```xml
<parent>
    <groupId>guru.nicks.commons</groupId>
    <artifactId>parent</artifactId>
    <version>...</version>
</parent>
```

Each module inheriting from this one must have `config/checkstyle.xml` in its root directory (not in the sources
directory), as compilation is preceded by calling Maven Checkstyle plugin.

The _maven-central_ profile eases deploy to Maven Central:\
`$ mvn clean deploy -Pmaven-central`

The GPG key ID (as per `gpg --list-keys`) is stored in `~/.m2/settings.xml` as follows:

```xml
<profiles>
    <profile>
        <id>maven-central</id>
        <properties>
            <gpg.keyname>...</gpg.keyname>
        </properties>
    </profile>
</profiles>     
```

## Disclaimer

THIS CODE IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED
TO THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. USE AT YOUR OWN RISK.

Copyright © 2025 [nicks.guru](https://nicks.guru). All rights reserved.
