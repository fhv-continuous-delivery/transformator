# Transformator
Transforms UML models to Java code. It uses [Eclipse Acceleo](https://projects.eclipse.org/projects/modeling.m2t.acceleo) to transorm an UML diagram into source code.

# Package repository
This repository uses <https://packagecloud.io> as the maven package repository

## Use the artifact

```
<repositories>
  <repository>
    <id>fhv-msi-continuous-delivery</id>
    <url>https://packagecloud.io/fhv-msi/continuous-delivery/maven2</url>
    <releases>
      <enabled>true</enabled>
    </releases>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
  </repository>
</repositories>

<dependency>
  <groupId>at.fhv.cicd</groupId>
  <artifactId>transformator</artifactId>
  <version>0.0.1-SNAPSHOT</version>
</dependency>
```

# Build
## Local build
Run the following maven command to build the artifact locally:

```
cp .travis.settings.xml $HOME/.m2/settings.xml
mvn org.eclipse.acceleo:org.eclipse.acceleo.maven:acceleo-compile install
```

## Remote build
Travis CI app is used to build the application. The build needs the following environment variables set in order to work:
* PACKAGECLOUD_TOKEN: This token is used to be able to deploy to packagecloud.io. The token can be found [here](https://packagecloud.io/fhv-msi/continuous-delivery/ci )