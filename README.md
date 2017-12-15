# Thor Analyzer 1.0

**The home for *Thor Analyzer* documentation.**

## Versions

Click [here](https://github.com/ChilliCream/thor-analyzer-docs) to get to the version overview.

## Source Code

The source code is maintained [here](https://github.com/ChilliCream/thor-analyzer).

## Topics

| Topic | Description |
| ----- | ----------- |
| [Getting Started](docs/GettingStarted.md) | A quickstart guide |
| [Extensibility](docs/Extensibility.md) | Explains the entensibility points |

## Rules

| Rule | Code | Description |
| ---- | ---- | ----------- |
| [ConstructionExceptionNotAllowed](docs/Rules/ConstructionExceptionNotAllowed.md) | R101 | Construction exceptions are not allowed |
| [DuplicateEventIdsNotAllowed](docs/Rules/DuplicateEventIdsNotAllowed.md) | R102 | Duplicate event identifiers are not allowed |
| [EventMustBeInvokable](docs/Rules/EventMustBeInvokable.md) | R103 | An event must be invokable |
| [EventMustBeInvokableWithDefaults](docs/Rules/EventMustBeInvokableWithDefaults.md) | R104 | An event must be able to handle default arguments |
| [EventParametersMustBeInOrder](docs/Rules/EventParametersMustBeInOrder.md) | R105 | Event parameters must be in the right order |
| [MustBeSealed](docs/Rules/MustBeSealed.md) | R201 | An event source class must be protected with `sealed` |
| [MustHaveSinglePrivateConstructor](docs/Rules/MustHaveSinglePrivateConstructor.md) | R202 | An event source must have a single private constructor |
| [MustHaveStaticLogProperty](docs/Rules/MustHaveStaticLogProperty.md) | R203 | An event source must have a static `Log` property |
| [MustHaveValidName](docs/Rules/MustHaveValidName.md) | R204 | An event source must have a valid name |