---
type: rule
title: Do you know the most popular unit testing frameworks for .NET Core
  applications?
uri: the-most-popular-unit-testing-frameworks-for-net-core-applications
authors:
  - title: Adam Cogan
    url: https://ssw.com.au/people/adam-cogan
  - title: Jason Taylor
    url: https://ssw.com.au/people/jason-taylor
related: []
redirects:
  - do-you-know-the-most-popular-unit-testing-frameworks-for-net-core-applications
created: 2020-03-16T20:05:20.000Z
archivedreason: null
guid: c7465c5f-45be-4185-ade6-836ff4d6b633
---
There are three main frameworks for unit testing. The good news is that they are all acceptable choices:

* They all have test runner packages for running tests directly from Visual Studio
* They all have console-based runners that can run tests as part of a CI/CD pipeline
* They differ slightly in syntax and feature set

<!--endintro-->

### xUnit.net – <mark>Recommended</mark>

[xUnit.net](https://xunit.net/) is a newer framework – written by the original creator of NUnit v2 to create a more opinionated and restrictive framework to encourage TDD best practice. For example, when running xUnit tests, the class containing the test methods is instantiated separately for each test so that tests cannot share data and can run in parallel.

xUnit.net is currently the most popular framework - and is even used by the .NET Core team.

However, one should note that XUnit is still using the old Assert standard, and should be augmented by a better assertion library, like [FluentAssertions](https://fluentassertions.com/) or [Shouldly](https://github.com/shouldly/shouldly).

xUnit.net is the default choice for .NET Core web applications and APIs at SSW.

### NUnit

The [NUnit](https://github.com/nunit/docs) project deserves recognition for being the first powerful and open-source unit test framework for the .NET universe – and it’s still a solid choice today. 

NUnit has undergone large changes in the last 10 years with its NUnit3 version.  The most notable is the Assert Constraints, which is a built-in Fluent Assertion library, allowing you to write readable asserts like `Assert.That(x, Is.EqualTo(42).Within(0.1))`. It has also adopted the lifetime scopes of XUnit, but you can choose which one to use. 

NUnit differs from XUnit in being more flexible and more adaptable versus XUnit being more restrictive and opinionated.

Because NUnit has an open-source .NET UI control for running tests, NUnit is still SSW’s preferred choice for embedding unit tests and a runner UI inside a Windows application.

### MSTest

[MSTest](https://docs.microsoft.com/en-us/visualstudio/test/getting-started-with-unit-testing) is Microsoft's testing framework. In the past this was a poor choice as although this was the easiest framework to run from Visual Studio, it was extremely difficult to automate these tests from CI/CD build servers. These problems have been completely solved with .NET Core but for most C# developers this is “too little, too late” and the other unit testing frameworks are now more popular.

### Mixing test frameworks

Dotnet is a flexible ecosystem, and that also applies to the use of test frameworks. There is nothing preventing you from using multiple different test frameworks in the same project. They will coexist with no pain. That way one can get the best from each, and not be locked-in with something that doesn't allow you to do your job efficiently.