#architecture #design #web #cqrs

- improves
	- [performance](/performance)
	- [scalability](/architecture/requirements/scalability.md)
	- [security](/security)
- alternativ design to vertical [layered architecture](/architecture/patterns/web/layered%20architecture.md)
- if DB interactions are slow this can be decoupled by CQRS
- send commands are stored in queue
	- executed over time
	- sequentially, not immediately

#### Application Areas
- do not simply edit and save customer address data freely, but "move" address
- all forms of data queries
- system with high collaboration often concurrent access by multiple users
- CQRS with [Event Sourcing](/Event%20Sourcing) provides complete log of all operations in the system

![single](/_diag/cqrs-single.png)

![split](/_diag/cqrs-split.png)

