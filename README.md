# [Nicks.Guru](https://nicks.guru) Commons Parent

Provides dependencies and build sequence for all other Commons modules. Can be used in other Spring Boot applications
as well:

- **Spring Boot & Spring Cloud** - core framework and microservices support
- **TestContainers** - integration testing with containerized databases
- **Camunda BPM** - business process management and workflow engine
- **AWS SDK** - Amazon Web Services integration
- **Other libraries** - security, monitoring, caching, and more

## Usage

Pick the most recent version from
[Maven Central](https://central.sonatype.com/namespace/guru.nicks.commons), then use as follows:

```xml
<parent>
    <groupId>guru.nicks.commons</groupId>
    <artifactId>parent</artifactId>
    <version>1.10.0</version>
</parent>
```

Each module inheriting from this one must have `config/checkstyle.xml` in its root directory (not in the sources
directory), as compilation is preceded by calling Maven Checkstyle plugin.

The _maven-central_ profile eases deploying to Maven Central:\
`$ mvn clean deploy -Pmaven-central`

The GPG key ID (as per `gpg --list-keys`) required for the deploying is stored in `~/.m2/settings.xml`:

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
