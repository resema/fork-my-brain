#gcp #google 


![[google-cloud-storage-portfolio.png]]

Contains:
- [[Cloud SQL]]
	- has a **storage limit**
- [[Cloud Spanner]]
	- **scales infinitely** compared to Cloud SQL
- [[Firestore]]
	- **managed** document store
	- **max. document size** 1Mb
	- NoSQL
- [[Cloud Bigtable]]
	- NoSQL
	- **scales infinitely**
	- good for **heavy read/write**
- [[Cloud Storage]]
	- **schemaless**
	- scales infinitely
	- **binary object data**
- [[BigQuery]]
	- fixed schema
	- **managed**
- [[Memorystore]]
	- **excellent for caching**
	- schemaless

- have different availability [[Service Level Agreement|SLA]], see also [[SLO, SLI and SLA]]
	- for the numbers see documentation
- **durability** represents the odds of losing data
	- preventing data loss is a shared responsibility
		- use the different possibilities offered
- amount of data and number of reads/writes is important when selecting a data storage service
	- some scale with [[horizontal scaling]]
	- some scale with [[vertical scaling]]
	- some scale with no limits
- Strong consistency is another factor
	- [[strong consistency]]
	- [[eventual consistency]]

See [[storage decision chart]] for help while choosing.