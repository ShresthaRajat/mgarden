# Cosmos DB
#cloud #Azure #databases 

Azure SQL Database is a high-performance, reliable, fully managed, and secure [relational database](relational%20database) based on the latest stable version of the [Microsoft SQL Server](Microsoft%20SQL%20Server) database engine provided by [Azure](Cloud%20Computing/Azure/Azure.md). 

Azure Cosmos DB is flexible as it stores data in atom-record-sequence (ARS) format which is then abstracted and projected as an API, which you specify when you're creating your database. Your choices include SQL, MongoDB, Cassandra, Tables, and Gremlin. This allows the user to keep the native API (i.e. no changes to the application code).

## Managed Database engines:
Azure provides fully managed database capabilities for SQLServer, MySQL and PostgreSQL databases which provides the following benifits:
-   Built-in high availability with no additional cost.
-   Predictable performance and inclusive, pay-as-you-go pricing.
-   Scale as needed, within seconds.
-   Ability to protect sensitive data at rest and in motion.
-   Automatic backups.
-   Enterprise-grade security and compliance.

### Azure Database for MySQL

Azure Database for MySQL offers several service tiers, and each tier provides different performance and capabilities to support lightweight to heavyweight database workloads. You can build your first app on a small database for a few dollars a month, then adjust the scale to meet the needs of your solution. Dynamic scalability enables your database to transparently respond to rapidly changing resource requirements. You only pay for the resources you need, and only when you need them.


### Azure Database for PostgreSQL

Azure Database for PostgreSQL is a relational database service in the cloud. The server software is based on the community version of the open-source PostgreSQL database engine. Your familiarity with tools and expertise with PostgreSQL is applicable when you're using Azure Database for PostgreSQL.

Azure Database for PostgreSQL is available in two deployment options: **Single Server** and **Hyperscale (Citus)**.

**Single Server**
All those capabilities require almost no administration, and all are provided at no additional cost. You can focus on rapid application development and accelerating your time to market rather than having to manage virtual machines and infrastructure. You can continue to develop your application with the open-source tools and platform of your choice, without having to learn new skills.

The Single Server deployment option offers three pricing tiers: Basic, General Purpose, and Memory Optimized. Each tier offers different resource capabilities to support your database workloads. You can build your first app on a small database for a few dollars a month, then adjust the scale to meet the needs of your solution. Dynamic scalability enables your database to transparently respond to rapidly changing resource requirements. You only pay for the resources you need, and only when you need them.

**Hyperscale (Citus)**
The Hyperscale (Citus) option horizontally scales queries across multiple machines by using sharding. Its query engine parallelizes incoming SQL queries across these servers for faster responses on large datasets. It serves applications that require greater scale and performance, generally workloads that are approaching, or already exceed, 100 GB of data.

The Hyperscale (Citus) deployment option supports multi-tenant applications, real-time operational analytics, and high-throughput transactional workloads. Applications built for PostgreSQL can run distributed queries on Hyperscale (Citus) with standard connection libraries and minimal changes.


### Azure SQL Managed Instance (MI) 

SQL Managed Instance (SQL MI) provides native Virtual Network (VNet) integration while Azure SQL Database enables restricted Virtual Network (VNet) access using [VNET](Cloud%20Computing/Azure/VNET.md) Endpoints and SQL MI also helps bridge the gap between Azure SQL Database and On-premises SQL Server due to being built on an instance scoped configuration model.

Azure SQL Managed Instance (MI) is similar to The Azure [SQL-Database](Cloud%20Computing/Azure/SQL-Database.md) on the following topics:
Management
1. Backup
2. Availability
3. Host Accessibility
4. License

However the key differences are:
**1. Recovery model**  
_Azure SQL Database_: From automated backups only.  
_SQL MI_: From automated backups and from full backups placed on Azure Blob Storage.

**2. Active Geo-replication**  
_SQL Database:_ Supported. In all service tiers other than Hyperscale.  
_SQL MI:_ Not supported. alternative solution is [Auto-failover groups](https://docs.microsoft.com/en-us/azure/azure-sql/database/auto-failover-group-overview).

**3. Auto-failover groups**  
_SQL Database:_ Supported. In all service tiers other than Hyperscale.  
_SQL MI:_ Supported.

**4. Auto-scale**  
_SQL Database:_ Only supported in Serverless model.  
_SQL MI:_ Not supported. You need to choose reserved compute and storage (vCore or max storage).

**5. Automatic tuning (indexes)**  
_SQL Database:_ Supported.  
_SQL MI:_ Not supported.

**6. Elastic jobs**  
_SQL Database:_ Supported.  
_SQL MI:_ Not supported. [SQL Agent](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/transact-sql-tsql-differences-sql-server#sql-server-agent) can be used instead.

**7. Long-term backup retention (LTR)**  
_SQL Database:_ Supported. keep automatically taken backups up to 10 years.  
_SQL MI:_ Not supported yet. Manual backups as a temporary workaround.

**8. Hyperscale architecture**  
_SQL Database:_ Supported.  
_SQL MI:_ Not supported.

**9. SQL Server Profiler**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.

**10. Cross-database transactions**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.

**11. Database mail (DbMail)**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.

**12. Linked servers**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.

**13. Service Broker**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.

**14. SQL Server Agent**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.

**15. SQL Server Auditing**  
_SQL Database:_ Not supported.  
_SQL MI:_ Supported.



## REFERENCES:
https://medium.com/awesome-azure/azure-difference-between-azure-sql-database-and-azure-sql-managed-instance-sql-mi-2e61e4485a65#:~:text=SQL%20Managed%20Instance%20(SQL%20MI)%20provides%20native%20Virtual%20Network%20(,an%20instance%20scoped%20configuration%20model.

### Azure database documentation

-   [Azure Analytics Services](https://azure.microsoft.com/product-categories/analytics/)
-   [Azure Cosmos DB documentation](https://learn.microsoft.com/en-us/azure/cosmos-db/)
-   [Azure SQL Database documentation](https://learn.microsoft.com/en-us/azure/sql-database/)
-   [Azure SQL Managed Instance documentation](https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/)
-   [Azure Database for MySQL documentation](https://learn.microsoft.com/en-us/azure/mysql/)
-   [Azure Database for PostgreSQL documentation](https://learn.microsoft.com/en-us/azure/postgresql/)

### Migrating database workloads to Azure

-   [Migrate SQL workloads to Azure](https://learn.microsoft.com/en-us/training/paths/migrate-sql-workloads-azure/)
-   [Migrate SQL Workloads to Azure SQL Databases](https://learn.microsoft.com/en-us/training/modules/migrate-sql-workloads-azure-sql-databases/)
-   [Migrate SQL Workloads to Azure SQL Managed Instances](https://learn.microsoft.com/en-us/training/modules/migrate-sql-workloads-azure-managed-instances/)
-   [Migrate on-premises MySQL databases to Azure Database for MySQL](https://learn.microsoft.com/en-us/training/modules/migrate-on-premises-mysql-databases/)

### Working with Azure databases

-   [Create an Azure Database for PostgreSQL server](https://learn.microsoft.com/en-us/training/modules/create-azure-db-for-postgresql-server/)
-   [Insert and query data in your Azure Cosmos DB database](https://learn.microsoft.com/en-us/training/modules/access-data-with-cosmos-db-and-sql-api/)
-   [Provision an Azure SQL database to store application data](https://learn.microsoft.com/en-us/training/modules/provision-azure-sql-db/)