#flutter #stateless

```plantuml
component "Input Data" as input
component "Widget" as widget
component "Renders UI" as ui

note right of input: Data can change (externally)
note right of ui: Gets (re-)rendered when Input Data changes

input -d-> widget
widget -d-> ui
```

see also [[stateful widget]]

it uses an internal state which extends [[State]]. The `State` classes and its [[derivative]] are **not** re-rendered with data changes (external.) `State` is a generic class which normally takes a type, like `State<MyApp>`.