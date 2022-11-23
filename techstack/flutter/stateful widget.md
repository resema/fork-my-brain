#flutter #stateful 

```plantuml
component "Input Data" as input
component "Widget" as widget
component "Renders UI" as ui

note right of input: Data can change (externally)
note right of ui: Gets (re-)rendered when Input Data  or local state changes

input -d-> widget
widget -d-> ui
```

see also [[stateless widget]]

### Change state
```dart
void setState(void Function() fn)
```
This `setState` function can change the wiget's internal state. It is a "trigger" that informs Flutter that it needs to re-run `build()` of the widget.

Internally Flutter is very efficient in re-drawing only important parts and not every pixel.