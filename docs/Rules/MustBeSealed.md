# MustBeSealed

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R201 | `BestPractice` | `Recommendation` |

## Reason

This rule breaks when the event source is not sealed.

### Noncompliant Example

```csharp
[EventSource(Name = "Noncompliant")]
public class NoncompliantEventSource // Noncompliant
    : EventSource
{
}
```

### Compliant Solution

```csharp
[EventSource(Name = "Compliant")]
public sealed class CompliantEventSource // Compliant
    : EventSource
{
}
```

## Solution

Make sure the class is protected with `sealed`.