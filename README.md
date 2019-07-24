# The Holon Platform

> Latest release: [5.2.14](#obtain-the-artifacts)

The [Holon Platform](https://holon-platform.com) is a __Java__ development ecosystem to create and maintain high quality, enteprise-grade web applications and services.

Some of the main platform key points are:

* __Provides "real" Java API__: the Holon platform is designed as a real Java API, with the aim to leverage all new Java 8 features and to create strong abstraction layers to ensure implementation details encapsulation, high productivity and long-term maintanability with a minimal application upgrade effort to follow the platform evolution.

* It's __modular and full-stack__ at the same time: the Holon platform provides a full-stack application development environment, but you can select only the components or modules you need and replace or extend them leveraging on the high configurability and extensibility features ensured by the platform architecture.

* The __`Property` data model__: the Holon platform property data model architecture allows to use an application data model which is independent from the persistence technology and make it a shared asset for all application layers, from the backend to the UI, avoiding code duplication and using a consistent API to manage it.

* It's __extensible by design__: the Holon platform components are designed to be highly extensible, configurable and integrable with other frameworks or libraries. This way it is the platform which must fit your needs, and not vice-versa.

The platform is organized in __modules__: each module corresponds to a GitHub repository and it is composed by a number of _artifacts_. All the modules depends from the _core_ module, and any other module (and its _artifacts_) can be used independently, to suit each project/application needs with a lightweight dependency set.

See the [Modules](#modules) section for a list of the available platform modules.

## Code structure

See [Holon Platform code structure and conventions](CODING.md) to learn about the _"real Java API"_ philosophy with which the project codebase is developed and organized.

## Getting started

### System requirements

The Holon Platform is built using __Java 8__, so you need a JRE/JDK version 8 or above to use the platform artifacts.

### Releases

See [releases](https://github.com/holon-platform/platform/releases) for the available releases.

#### 5.2.x release notes

See [What's new in version 5.2.x](https://docs.holon-platform.com/current/reference/#WhatsNew52x) to learn about the new features and API operations of the 5.2 minor release.

### Platform distribution versioning

The Holon platform use the [Semantic Versioning](http://semver.org) system and each platform _module_ is versioned following the semantic versioning convention.

The platform distribution artifact, which contains the Maven _BOM (Bill Of Materials)_ to provide all the platform modules artifacts, is bound to all the __latest modules version__ at the platform release time. For this reason, the following convention is used for the platform distribution versioning:

* When a new platform _module_ version is released, a new platform distribution version is released too, and the platform overall version is incremented according to the _module_ version: if it is a _patch version_ release, the platform _patch version_ is incremented; if it is a _minor version_ release, the platform _minor version_ is incremented instead.

* When more than one platform _module_ version changes, the most significative version change is taken into account: if the _minor version_ of a module is changed, the platform _minor version_ is incremented; if only the _patch version_ of the modules is changed, the platform _patch version_ is incremented instead.

* The platform _major version_ number is incremented for breaking and not backward-compatible API changes. In this case, all the platform _modules_ will be versioned with the new  _major version_ number.

* The platform _patch version_ number can be incremented even if there are not any module version changes, for example to release a documentation or BOM project fix.

### Obtain the artifacts

The [Holon Platform](https://holon-platform.com) is open source and licensed under the [Apache 2.0 license](LICENSE.md). All the artifacts (including binaries, sources and javadocs) are available from the [Maven Central](https://mvnrepository.com/repos/central) repository.

The easiest way to obtain the Holon Platform artifacts is by using the __platform BOM (Bill Of Materials)__, which provides a complete set of dependencies of the latest release of each module.

_Platform Maven BOM:_
```xml
<dependencyManagement>
    <dependency>
        <groupId>com.holon-platform</groupId>
        <artifactId>bom</artifactId>
        <version>5.2.14</version>
        <type>pom</type>
        <scope>import</scope>
    </dependency>
</dependencyManagement>
```

With the platform _BOM_ imported in your dependency management section, you can declare and obtain the artifacts you need without specifying the artifact version, which will be the latest version provided by the platform _BOM_. For example:

_Declaring the holon-core dependency:_
```xml
<dependencies>
  <dependency>
    <groupId>com.holon-platform.core</groupId>
    <artifactId>holon-core</artifactId>
  </dependency>
</dependencies>
```

See the [Modules](#modules) section for a list of the available platform modules.

## Getting help

* Check the [platform documentation](https://docs.holon-platform.com/current/reference).

* Explore the [Holon platform website](https://holon-platform.com) for tutorials, learning resources, news and articles.

* Ask a question on [Stack Overflow](http://stackoverflow.com). We monitor the [`holon-platform`](http://stackoverflow.com/tags/holon-platform) tag.

* A [commercial support](https://holon-platform.com/services) is available too.

## Examples

See the [Holon Platform examples](https://github.com/holon-platform/holon-examples) repository for a set of example projects.

## Contribute

See [Contributing to the Holon Platform](https://github.com/holon-platform/platform/blob/master/CONTRIBUTING.md).

[![Gitter chat](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/holon-platform/contribute?utm_source=share-link&utm_medium=link&utm_campaign=share-link) 
Join the __contribute__ Gitter room for any question and to contact us.

## License

All the [Holon Platform](https://holon-platform.com) modules are _Open Source_ software released under the [Apache 2.0 license](LICENSE).

## Modules

* [Holon Core module](https://github.com/holon-platform/holon-core)
* [Holon Reactor module](https://github.com/holon-platform/holon-reactor)
* [Holon JSON module](https://github.com/holon-platform/holon-json)
* [Holon JAX-RS module](https://github.com/holon-platform/holon-jaxrs)
* [Holon JDBC module](https://github.com/holon-platform/holon-jdbc)
* [Holon JPA module](https://github.com/holon-platform/holon-jpa)
* [Holon JDBC Datastore module](https://github.com/holon-platform/holon-datastore-jdbc)
* [Holon JPA Datastore module](https://github.com/holon-platform/holon-datastore-jpa)
* [Holon JPA QueryDSL module](https://github.com/holon-platform/holon-datastore-jpa-querydsl)
* [Holon MongoDB Datastore module](https://github.com/holon-platform/holon-datastore-mongo)
* [Holon Vaadin Flow module](https://github.com/holon-platform/holon-vaadin-flow)
* [Holon Vaadin 8 module](https://github.com/holon-platform/holon-vaadin)
* [Holon Vaadin 7 module](https://github.com/holon-platform/holon-vaadin7)
