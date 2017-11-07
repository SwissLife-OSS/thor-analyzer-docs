# EventParametersMustBeInOrder

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R105 | `Required` | `Critical` |

## Reason

This rule breaks when the event parameter order does not match the `WriteEvent` call parameter order.

### Noncompliant Example

```csharp
[EventSource(Name = "Noncompliant")]
public class NoncompliantEventSource
    : EventSource
{
    [Event(1)]
    public void Foo(int foo, string bar)
    {
        WriteEvent(1, bar, foo); // Noncompliant
    }
}
```

### Compliant Solution

```csharp
[EventSource(Name = "Compliant")]
public class CompliantEventSource
    : EventSource
{
    [Event(1)]
    public void Foo(int foo, string bar)
    {
        WriteEvent(1, foo, bar); // Compliant
    }
}
```

## Solution

Always ensure the event parameter order matches the `WriteEvent` call parameter order.