There are four primary storage classes
- Standard storage
	- frequently accessed, or “hot,” data
	- data that’s stored for only brief periods of time
- Nearline storage
	- Once per month
	- storing infrequently accessed data, like reading or modifying data on average once a month or less
	- Examples
		- data backups
		- long-tail multimedia content
		- data archiving
- Coldline Storage
	- Once every 90 days
	- low-cost option for storing infrequently accessed data
	- meant for reading or modifying data, at most, once every 90 days
- Archival Storage
	- Once a year
	- lowest-cost option, used ideally for data archiving, online backup, and disaster recovery

Common characteristics across all four storage classes
- Unlimited storage (no min object size)
- Worldwide accessibility and locations
- Low latency and high durability
- A uniform experience, which extends to security, tools, and APIs
- Geo-redundancy
	- if data is stored in a multiple-region and dual-region

Autoclass
- A Cloud Storage feature
	- Move data that is not accessed to colder storage classes to reduce storage cost
	- Moves data that is accessed to Standard storage to optimize future accesses
- Simplifies and automates cost saving for Cloud Storage data

Cloud Storage Fee
- Pay only for what you use - no minimum fee
- No prior provisioning of capacity
- Security perspective (no additional charge)
	- Encrypts data on the server side (before data written into the disk)
	- Use of HTTPS/TLS (Transport Layer Security) (data travelling between customers device and Google is encrypted)

Bring data into Cloud Storage
- Online transfer (use gcloud storage - a command from Cloud SDK)
- Storage Transfer Service (upload terabytes or even petabytes of data quickly and cost-effectively)
- Transfer Appliance

Cloud Storage’s tight integration with other Google Cloud products and services means that there are many additional ways to move data into the service
- can import and export tables to and from both BigQuery and Cloud SQL
- store App Engine logs, Firestore backups, and objects used by App Engine applications, like images
- store instance startup scripts, Compute Engine images, and objects used by Compute Engine applications

