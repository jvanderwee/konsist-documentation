---
description: https://docs.konsist.lemonappdev.com/
---

# What is Konsist?

Konsist is a library that helps to guard [Kotlin](https://kotlinlang.org/) codebase consistency. It facilitates the standardization of the Kotlin codebase by enforcing coding conventions and guarding project architecture.&#x20;

Konsist tests are written in Kotlin. Here is a simple test that verifies if every use case class resides in `usecase` package:

```kotlin
@Test
fun `every use case reside in use case package`() {
    KoScope
        .fromProject() // Define scope using all Kotlin files present in the project
        .classes() // Map to list of classes
        .withNameSuffix("UseCase") // Filter classes heaving name ending with 'UseCase'
        .assert { it.resideInPackages("..usecase..") } // Assert use case
}
```

Konsist works with any test framework that executes Kotlin code such as [JUni4](https://junit.org/junit4/) and [JUnit5](https://junit.org/junit5/).

Take a look at the [gettingstarted.md](getting-started/gettingstarted.md "mention") page to learn how to set up Konsist or go straight to the [Broken link](broken-reference "mention") section to review the examples.&#x20;
