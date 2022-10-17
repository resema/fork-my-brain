#flutter

```plantuml
component "Input Data" as input
component "Widget" as widget
component "Renders UI" as ui

note right of input: Data can change (externally)
note right of ui: Gets (re-)rendered when Input Data changes

input -d-> widget
widget -d-> ui
```