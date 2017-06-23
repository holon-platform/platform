# Holon Platform code structure and conventions

## Introduction

The [Holon Platform](https://holon-platform.com) is developed with the intention of realizing a _real Java API_. 
With _real_ we mean a Java codebase which can be accessed and used just through Java `interface` methods.

All this to achieve the following goals and benefits:

* __High maintainability__: The `interface`'s concrete implementations are "hidden" to the developer which uses the platform code and there is no need (and no temptation...) to directly use or even extend the concrete implementation classes. This way, the code written using the platform libraries is essentially isolated from the implementation classes and immune to changes to such classes in future releases, as long as there is not any breaking API changes.

* __Easiness of use and productivity__: Each API `interface` provides suitable creation/building methods to obtain the concrete implementation objects, using a _fluent_ building paradigm when appropriate. This eliminate the need to know which class has to be used as interface implementation and where to locate it.

* __Extensibility__: Using `interface`s, by nature, favours and facilitate extensibility and integration.

## Technology

This approach leverages on the `interface`s extensions and new features introduced by __Java 8__, such as `static` and `default` methods.

Besides `interface` extensions, other powerful and useful __Java 8__ features are used whenever possible and meaningful. In particular:

* _Functional_ interfaces
* `Stream`s
* `Optional`s
* The new [Date and time API](http://www.oracle.com/technetwork/articles/java/jf14-date-time-2125367.html)

## API interface rules

The following rules are followed when creating an API interface:

* Any method which returns a value that can be `null`, must return an `Optional` of such value.
* Any method which returns a `Collection` must return an _empty_ `Collection` instead of `null`.
* When one or more implementation class in available, the interface must provide one or more _building_ method to obtain and configure an implementation instance:
	* If the implementation class does not need any required configuration parameter (or they are just one or two), a direct creation `static` method (typically named `create()`) must be provided;
	* If the implementation class requires or supports a set of configuration parameters, a _fluent_ builder instance must be provided through a `static` method, conventionally named `builder()`.
* Any _constant_ value must be made available by `static final` attributes of the interface.

## Packages conventions

The _packages_ of each artifact must be organized as follows:

* The artifact _group id_ as prefix
* A name (simple or composed) which represents the API topic, which contains the __public API__ `interface`s
* The word __internal__ followed by the API topic name, which contains the implementation and support classes

For example, using the `com.holonplatform.core` _group id_, the classes of an API topic named `mytopic` are organized in packages named this way:

* `com.holonplatform.core`**`.mytopic`**: API interfaces
* `com.holonplatform.core`**`internal.mytopic`**: Implementation and support classes
