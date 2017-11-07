# DuplicateEventIdsNotAllowed

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R102 | `Required` | `Critical` |

## Reason

This rule breaks when one or more event identifier are reused.

### Noncompliant Example

```csharp
[EventSource(Name = "Noncompliant")]
public class NoncompliantEventSource
    : EventSource
{
    [Event(1)]
    public void First(string foo)
    {
        WriteEvent(1, foo);
    }

    [Event(1)] // Noncompliant
    public void Second(string bar)
    {
        WriteEvent(1, bar); // Noncompliant
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
    public void First(string foo)
    {
        WriteEvent(1, foo);
    }

    [Event(2)] // Compliant
    public void Second(string bar)
    {
        WriteEvent(2, bar); // Compliant
    }
}
```

## Solution

The event id is unique within one event source. Therefore, it has to be ensured it is used once. Also to be mentioned is to start with `1` and not `0` like in `array`s.