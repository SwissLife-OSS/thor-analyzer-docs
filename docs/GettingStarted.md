# Getting Started

Getting started in two steps. Install the *NuGet* package and start writing code. That´s it.

## Install Package

Before we start we have to decide which package would be the right choice for our project. If we work with the `System.Diagnostics.Tracing` namespace in combination with *.Net* 4.6.1 or higher, we might be well adviced by using the `Thor.Analyzer` package. But if we use the `Microsoft.Diagnostics.Tracing` namespace in combination with *.Net* 4.5.1 or higher instead, we should choose the `Thor.Analyzer.Legacy` package.

In summary, can be stated that newer projects using the `System.Diagnostics.Tracing` namespace should install the `Thor.Analyzer` package. See the following Powershell script.

```powershell
Install-Package Thor.Analyzer
```

Therefore, older projects using the `Microsoft.Diagnostics.Tracing` namespace should install the `Thor.Analyzer.Legacy` package. See the following Powershell script.

```powershell
Install-Package Thor.Analyzer.Legacy
```

## Basic Example

This example shows a simple tercet.

```csharp
MyCustomEventSource eventSource = new MyCustomEventSource();
EventSourceAnalyzer analyzer = new EventSourceAnalyzer();
Report report = analyzer.Inspect(eventSource);
```

The report contains all the important information we need. If we want to know whether the event schema contains any errors, we can do so by checking the `HasErrors` property.

## Automated Test Example

This example shows how to automate the analysis of event sources. For this example we used *xUnit*, but any other test framework will work pretty much the same.

```csharp
[Fact(DisplayName = "Should not contain any error")]
public void Analyze()
{
    // Arrange
    MyCustomEventSource eventSource = MyCustomEventSource.Log;
    EventSourceAnalyzer analyzer = new EventSourceAnalyzer();

    // Act
    Report report = analyzer.Inspect(eventSource);

    // Assert
    Assert.False(report.HasErrors);
}
```