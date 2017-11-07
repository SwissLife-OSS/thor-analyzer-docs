# MustHaveSinglePrivateConstructor

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R202 | `BestPractice` | `Recommendation` |

## Reason

This rule breaks when event source has not a single and empty private constructor.

### Noncompliant Example

```csharp
[EventSource(Name = "Noncompliant")]
public class NoncompliantEventSource
    : EventSource
{
    // Noncompliant
}
```

### Compliant Solution

```csharp
[EventSource(Name = "Compliant")]
public class CompliantEventSource
    : EventSource
{
    // Compliant
    private CompliantEventSource() { }
}
```

## Solution

Make sure there is only one and empty constructor without parameters.