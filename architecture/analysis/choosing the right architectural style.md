#architecture #cheat #web

### Requirements & Considerations
[[Software Architecture]] is mostly based on [[three pillars of architecture|three pillars]] (due to CPSA)
- [[functional requirement]]s
	- *"Is something writeable as a user story?"*
- [[quality requirements]] (non-functional requirements)
- [[limiting factors]]
	- *"Normally just facts!"*


```plantuml
@startuml
component "determine goals and limiting factors" as goals
component "description of architecture" as desc
component "preselection of all suitable options" as opt
component "researching consequences and evaluation of those options" as research

goals -d-> opt
goals -[hidden]r-desc
desc -d-> opt
opt -d-> research
@enduml
```

Use [[design principles]] and [[software architecture patterns]] to define a possible solution.

See also [[Web Architecture Layers]]

Chosing a [[REST]]ful style, see [here](https://letmegooglethat.com/?q=awesome+REST)
