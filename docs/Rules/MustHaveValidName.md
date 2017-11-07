# MustHaveValidName

| Code | Rule Set | Type |
| ---- | -------- | ---- |
| R204 | `BestPractice` | `Recommendation` |

## Reason

This rule breaks when the event source has a invalid name.

### Noncompliant Example

```csharp
[EventSource(Name = "123_Noncompliant")] // Noncompliant
public class NoncompliantEventSource
    : EventSource
{
}
```

### Compliant Solution

```csharp
[EventSource(Name = "Compliant-Events")] // Compliant
public class CompliantEventSource
    : EventSource
{
}
```

## Solution

Make sure the event source name is valid. The name is validated with the following regular expression `^[a-zA-Z]+(\-[a-zA-Z]+)*$`. This means characters from `A-Z` and dashes `-` as separators. Also a good practise is to use this pattern `Company-Product-Component`.