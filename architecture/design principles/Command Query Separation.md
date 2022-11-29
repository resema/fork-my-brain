#architecture #design #strategy #web #cqs

- separation of methods or software architecture into two parts
	- commands: change system state, no return values
	- queries: return values but no system state changes
- Exceptions: read/remove from a stack
  ==> query with change of state
- [Command Query Responsibility Segregation](/architecture/patterns/web/Command%20Query%20Responsibility%20Segregation.md) aka CQRS