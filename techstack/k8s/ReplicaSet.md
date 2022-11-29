#gcp #cloud #kubernetes #k8s 

ReplicaSet object automates the creation and management of [pod](/techstack/gcp/pod.md) replicas. 
- represents a group of pod replicas
- replicas are exact copies of a [pod](/techstack/gcp/pod.md)

```plantuml
@startuml
top to bottom direction

component Service as svc
component Pod as p1
component Pod as p2
component Pod as p3
component ReplicaSet as set

svc -u-> p1
svc -r-> p2
svc --> p3
set .u.> p1
set .l.> p2
set ..> p3

p1 -[hidden]d-> p2
p2 -[hidden]d-> p3
@enduml
```
