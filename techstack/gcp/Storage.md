#gcp #google 


![google-cloud-storage-portfolio](/_img/google-cloud-storage-portfolio.png)

Contains:
- [Cloud SQL](/Cloud%20SQL)
	- has a **storage limit**
- [Cloud Spanner](/Cloud%20Spanner)
	- **scales infinitely** compared to Cloud SQL
- [Firestore](/techstack/google/Firestore.md)
	- **managed** document store
	- **max. document size** 1Mb
	- NoSQL
- [Cloud Bigtable](/Cloud%20Bigtable)
	- NoSQL
	- **scales infinitely**
	- good for **heavy read/write**
- [Cloud Storage](/Cloud%20Storage)
	- **schemaless**
	- scales infinitely
	- **binary object data**
- [BigQuery](/BigQuery)
	- fixed schema
	- **managed**
- [Memorystore](/Memorystore)
	- **excellent for caching**
	- schemaless

- have different availability [SLA](/Service%20Level%20Agreement), see also [SLO, SLI and SLA](/architecture/requirements/SLO,%20SLI%20and%20SLA.md)
	- for the numbers see documentation
- **durability** represents the odds of losing data
	- preventing data loss is a shared responsibility
		- use the different possibilities offered
- amount of data and number of reads/writes is important when selecting a data storage service
	- some scale with [horizontal scaling](/techstack/gcp/horizontal%20scaling.md)
	- some scale with [vertical scaling](/techstack/gcp/vertical%20scaling.md)
	- some scale with no limits
- Strong consistency is another factor
	- [strong consistency](/strong%20consistency)
	- [eventual consistency](/eventual%20consistency)

See [storage decision chart](/techstack/gcp/storage%20decision%20chart.md) for help while choosing.