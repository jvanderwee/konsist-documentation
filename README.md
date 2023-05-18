# What is Konsist?

![](.gitbook/assets/konsist-logo.png)

Konsist is a static code analyzer for [Kotlin](https://kotlinlang.org/) language. It facilitates the standardization of the Kotlin codebase by enforcing coding conventions and guarding project consistency.&#x20;

Konsist tests are written in Kotlin and run as unit tests. Here is a simple test that verifies if every use case class resides in `domain.usecase` package:

```kotlin
@Test
fun `every use case reside in use case package`() {
    Konsist
        .scopeFromProject() // Define scope using all Kotlin files present in the project
        .classes() // Get all classes
        .withNameSuffix("UseCase") // Filter classes heaving name ending with 'UseCase'
        .assert { it.resideInPackages("com.app.domain.usecase") } // Assert class has com.app.domain.usecase package
}
```

Look at the [gettingstarted.md](getting-started/gettingstarted.md "mention") page to learn how to set up Konsist or go straight to the [Broken link](broken-reference "mention") section to review examples of Konsist tests.&#x20;
