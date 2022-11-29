#gcp #deployment 

if you don't want multiple versions of a [service](/techstack/gcp/service.md) running simultaneously
- blue [deployment](/deployment) is the current verison
- gree [deployment] is the new environment
- once tested, migrate client request
- if failures occur, switch back