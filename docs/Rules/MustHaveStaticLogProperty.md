# MustHaveStaticLogProperty

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R203 | `BestPractice` | `Recommendation` |

## Reason

This rule breaks when the event source has no `Log` field.

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
    public static readonly CompliantEventSource Log = new CompliantEventSource();
}
```

## Solution

Make sure the event source has a `public`, `static` and `readonly` `Log` field.