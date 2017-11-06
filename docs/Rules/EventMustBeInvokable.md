# EventMustBeInvokable

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R103 | `Required` | `Critical` |

## Reason

This rule breaks when the event does not call `WriteEvent` or the call is bypassed due to incorrect filtering before the `WriteEvent` call.

### Noncompliant Example

```csharp
[EventSource(Name = "NoncompliantEventSource")]
public class NoncompliantEventSource
    : EventSource
{
    [Event(1)]
    public void Foo(string bar)
    {
        // Noncompliant
    }
}
```

### Compliant Solution

```csharp
[EventSource(Name = "CompliantEventSource")]
public class CompliantEventSource
    : EventSource
{
    [Event(1)]
    public void Foo(string bar)
    {
        WriteEvent(1, bar); // Compliant
    }
}
```

## Solution

Always ensure events call `WriteEvent`. Only exception is when the event is disabled.