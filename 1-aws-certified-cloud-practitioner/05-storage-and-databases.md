# 5. Storage and Databases

## 🏷 Instance stores and Amazon Elastic Block Store (Amazon EBS)
### Instance stores
An `instance store` provides `temporary block-level storage` for an `Amazon EC2 instance`. An instance store is disk storage that is `physically attached` to the host computer for an `EC2 instance`, and therefore `has the same lifespan as the instance`. When the instance is terminated, you `lose any data in the instance store`.

### Amazon Elastic Block Store (Amazon EBS)
`Block-level storage` volumes behave like `physical hard drives`. `Amazon Elastic Block Store (Amazon EBS)` is a service that provides `block-level storage` volumes that you can use with `Amazon EC2 instances`. If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume `remains available`. To create an EBS volume, you define the configuration (such as volume size and type) and provision it. After you create an EBS volume, it `can attach to an Amazon EC2 instance`. Because EBS volumes are `for data that needs to persist`, it’s important to `back up` the data. You can take `incremental backups` of EBS volumes by creating `Amazon EBS snapshots`.

When you modify a file in `block storage`, only the pieces that are `changed` are updated. 

### Amazon EBS snapshots
An `EBS snapshot` is an `incremental backup`. This means that the first backup taken of a volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved. `Incremental backups` are different from `full backups`, in which all the data in a storage volume copies each time a backup occurs. The full backup includes data that has not changed since the most recent backup.

## 🏷 Amazon Simple Storage Service (Amazon S3)
### Object storage
In `object storage`, each object consists of `data`, `metadata`, and `a key`. The data might be an image, video, text document, or any other type of file. Metadata contains information about what the data is, how it is used, the object size, and so on. An object’s `key` is its `unique identifier`.

When a file in `object storage` is `modified`, `the entire object is updated`.

### Amazon Simple Storage Service (Amazon S3)
`Amazon Simple Storage Service (Amazon S3)` is a service that provides `object-level storage`. Amazon S3 stores data as objects in `buckets`. You can upload any type of file to Amazon S3, such as images, videos, text files, and so on. For example, you might use Amazon S3 to store backup files, media files for a website, or archived documents. Amazon S3 offers unlimited storage space. The `maximum file size` for an `object` in` Amazon S3` is `5 TB`.

When you upload a file to Amazon S3, you can set `permissions` to control `visibility and access` to it. You can also use the Amazon S3 `versioning` feature to `track changes to your objects` over time. 

### Amazon S3 storage classes
With Amazon S3, you pay only for what you use. You can choose from a range of storage classes to select a fit for your business and cost needs. When selecting an Amazon S3 storage class, consider these two factors:
- How often you plan to retrieve your data
- How available you need your data to be

**S3 Standard**
- Designed for `frequently accessed data`
- Stores data in a `minimum of three Availability Zones`

S3 Standard provides `high availability` for objects. This makes it a good choice for a wide range of use cases, such as websites, content distribution, and data analytics. S3 Standard has a `higher cost` than other storage classes intended for infrequently accessed data and archival storage.

**S3 Standard-Infrequent Access (S3 Standard-IA)**
- Ideal for `infrequently` accessed data
- Similar to S3 Standard but has a `lower storage price` and `higher retrieval price`

S3 Standard-IA is ideal for data `infrequently accessed` but `requires high availability when needed`. Both S3 Standard and S3 Standard-IA store data in a `minimum of three Availability Zones`. 

**S3 One Zone-Infrequent Access (S3 One Zone-IA)**
- Stores data in `a single Availability Zone`
- Has a `lower storage price` than S3 Standard-IA

This makes it a good storage class to consider if the following conditions apply:
- You want to save costs on storage.
- You can easily reproduce your data in the event of an Availability Zone failure.

**S3 Intelligent-Tiering**
- Ideal for data with `unknown or changing access patterns`
- Requires a small monthly monitoring and automation `fee` per object

In the S3 Intelligent-Tiering storage class, Amazon S3 monitors objects’ access patterns. If you haven’t accessed an object for `30 consecutive days`, Amazon S3 automatically moves it to the `infrequent access tier, S3 Standard-IA`. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the `frequent access tier, S3 Standard`.

**S3 Glacier**
- `Low-cost` storage designed for `data archiving`
- Able to retrieve objects within `a few minutes to hours`

For example, you might use this storage class to store archived customer records or older photos and video files.

**S3 Glacier Deep Archive**
- `Lowest-cost` object storage class ideal for `archiving`
- Able to retrieve objects `within 12 hours`

When deciding between Amazon S3 Glacier and Amazon S3 Glacier Deep Archive, consider `how quickly` you need to `retrieve` archived objects. 

## 🏷 Amazon Elastic File System (Amazon EFS)
### File storage
In `file storage`, `multiple clients` (such as users, applications, servers, and so on) can access data that is stored in `shared` file folders. In this approach, a storage server uses `block storage` with a local file system to organize files. Clients access data through file paths.

Compared to block storage and object storage, file storage is ideal for use cases in which `a large number of services and resources` need to `access the same data` `at the same time`.

`Amazon Elastic File System (Amazon EFS)` is a `scalable` file system used with AWS `Cloud` services and `on-premises` resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to `petabytes` without disrupting applications.
 
### Comparing Amazon EBS and Amazon EFS
An `Amazon EBS` volume stores data in a `single Availability Zone`. To attach an Amazon EC2 instance to an EBS volume, both the Amazon `EC2` instance and the `EBS` volume must reside within `the same Availability Zone`.

`Amazon EFS` is a `regional` service. It stores data in and across `multiple Availability Zones`.  The duplicate storage enables you to access data `concurrently` from `all the Availability Zones` in the Region where a file system is located. Additionally, `on-premises` servers can access `Amazon EFS` using `AWS Direct Connect`.

## 🏷 Amazon Relational Database Service (Amazon RDS)
### Relational databases
Relational databases use structured query language (SQL) to store and query data. This approach allows data to be stored in an easily understandable, consistent, and scalable way. 
### Amazon Relational Database Service
Amazon `Relational Database Service (Amazon RDS)` is a service that enables you to run `relational databases` in the AWS Cloud.

Amazon RDS is a `managed service` that automates tasks such as hardware provisioning, database setup, patching, and backups. With these capabilities, you can spend less time completing administrative tasks and more time using data to innovate your applications. You can `integrate` Amazon RDS with `other services` to fulfill your business and operational needs, such as using `AWS Lambda` to query your database from a serverless application.

Amazon RDS provides a number of different security options. Many Amazon RDS database engines offer `encryption at rest` (protecting data while it is stored) and `encryption in transit` (protecting data while it is being sent and received).

### Amazon RDS database engines
`Amazon RDS` is available on six `database engines`, which optimize for memory, performance, or input/output (I/O). Supported database engines include:
- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

### Amazon Aurora
`Amazon Aurora` is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational databases. It is up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases. Amazon Aurora helps to `reduce your database costs` by `reducing unnecessary input/output (I/O)` operations, while ensuring that your database resources remain reliable and available. Consider Amazon Aurora if your workloads require `high availability`. It replicates `six copies of your data across three Availability Zones` and continuously `backs up` your data to Amazon S3.

## 🏷 Amazon DynamoDB
### Nonrelational databases
In a nonrelational database, you create tables. A table is a place where you can store and query data. Nonrelational databases are sometimes referred to as `“NoSQL databases”` because they use structures other than rows and columns to organize data. One type of structural approach for nonrelational databases is `key-value pairs`. With key-value pairs, data is organized into items (keys), and items have attributes (values). 

In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes. 

### Amazon DynamoDB
`Amazon DynamoDB` is a `key-value database service`. It delivers single-digit millisecond performance at any scale.

- DynamoDB is `serverless`, which means that you do not have to provision, patch, or manage servers. You also do not have to install, maintain, or operate software.
- As the size of your database shrinks or grows, DynamoDB `automatically scales` to adjust for changes in capacity while maintaining consistent performance. This makes it a suitable choice for use cases that require high performance while scaling.

## 🏷 Amazon Redshift
`Amazon Redshift` is a `data warehousing service` that you can use for `big data analytics`. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.

## 🏷 AWS Database Migration Service
### AWS Database Migration Service (AWS DMS)
`AWS Database Migration Service (AWS DMS)` enables you to migrate relational databases, nonrelational databases, and other types of data stores. With AWS DMS, you move data between a `source database` and a `target database`. The source and target databases can be of the `same type` or `different types`. During the migration, your source database remains operational, reducing downtime for any applications that rely on the database. 

### Other use cases for AWS DMS
- `Development and test database migrations`: Enabling developers to test applications against production data without affecting production users
- `Database consolidation`: Combining several databases into a single database
- `Continuous replication`: Sending ongoing copies of your data to other target sources instead of doing a one-time migration

## 🏷 Additional database services
### Amazon DocumentDB
`Amazon DocumentDB` is a `document database service` that supports `MongoDB` workloads. 

### Amazon Neptune
`Amazon Neptune` is a `graph database service`. You can use Amazon Neptune to build and run applications that work with `highly connected datasets`, such as recommendation engines, fraud detection, and knowledge graphs.

### Amazon Quantum Ledger Database (Amazon QLDB)
`Amazon Quantum Ledger Database (Amazon QLDB)` is a ledger database service. You can use Amazon QLDB to `review a complete history of all the changes that have been made` to your application data.

### Amazon Managed Blockchain
`Amazon Managed Blockchain` is a service that you can use to create and manage blockchain networks with open-source frameworks. Blockchain is a `distributed ledger system` that lets multiple parties run transactions and share data `without a central authority`.

### Amazon ElastiCache
`Amazon ElastiCache` is a service that `adds caching layers on top of your databases` to help improve the `read times` of common requests. It supports two types of data stores: `Redis` and `Memcached`.

### Amazon DynamoDB Accelerator
`Amazon DynamoDB Accelerator (DAX)` is an `in-memory cache` for `DynamoDB`. It helps improve `response times` from single-digit milliseconds to microseconds.
















