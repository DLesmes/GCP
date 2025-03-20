### [Home](https://github.com/DLesmes/GCP/blob/main/README.md#google-cloud-tools)
---

# Storage on GCP
## Services comparisson
![](https://static.platzi.com/media/user_upload/Screenshot_26-ff620129-2ba2-4c0f-aa8e-78aa6f91cfab.jpg)

## Storage Decision Tree
![](https://1.bp.blogspot.com/-H4a0slANRLg/XXFGsDshuKI/AAAAAAAAAAU/Ov1pyV1IOqQJvSfTJy50eL6dGCrCBHk-wCLcBGAs/s1600/storageoptions.jpg)

## Creating a Bucket in Google Cloud Storage 🪣☁️

Managing cloud storage, especially in Google Cloud Storage, starts with creating a bucket. This is fundamental for ensuring your data is stored efficiently and securely.  To access Cloud Storage, go to the hamburger menu (☰) in the top left corner of the Google Cloud Console and find "Cloud Storage."

**Choosing a Unique Bucket Name: Why It Matters**

When creating a bucket, picking a *unique* name is crucial. Guarantee uniqueness by including your project's unique identifier and additional descriptive words. For example, a name like `project-id-bucket-one`.

**Bucket Location Settings: Where Your Data Lives 🌎**

Several location settings are available:

* **Multi-regional:** Data is distributed across multiple regions for maximum availability. 🌎🌎🌎
* **Dual-region:** Data is split between two nearby locations for improved access and redundancy. 🌎🌎
* **Regional:** Data is stored in a single region, which can be more cost-effective. 🌎

Choosing the right location depends on where your end-users or services accessing the data are located.  Think global, act local!

**Running from gsutil**
```bash
gsutil mb -c standard -l us --pap enforced -b on --retention 10y gs://gemb-platzi-storage-bucket-01
```

**Where** `-c` is the class `-l` is the type of location we want `--pap` specifies public access `-b` is to enable uniform access Advanced: `--retention` is the retention period for the resource.

**Calculating Storage Costs 💰**

Use the cost calculator in the console to estimate storage expenses based on your configurations. Prices vary based on gigabytes stored and location:

* **Regional:** Storing 1,000 GB costs around $20 per month.
* **Dual-region:** Costs about $36 per month.
* **Multi-regional:** Costs approximately $26 per month.

Consider these costs when choosing your storage setup to optimize spending.

**Storage Classes:  Balancing Access and Cost**

Storage classes define how and when you can access your data:

* **Standard:**  Perfect for frequently accessed data. ⚡
* **Nearline:**  Suitable for data accessed less regularly (e.g., once a month). 🗓️
* **Coldline:** Designed for infrequently accessed data, with lower storage fees but higher retrieval costs. 🗄️
* **Archive:**  Best for long-term data retention with very infrequent access. 💾

Each class has different cost implications, so choose wisely to save money.

**Securing Your Data in Google Cloud Storage 🔒**

Setting access control policies is vital:

* **Public Access:**  You can choose whether objects are publicly accessible.  For sensitive data, *avoid* public access to prevent leaks! ⛔
* **Access Policies:**  Define access rules, either globally for all objects in a bucket or for specific objects. 

Proper security configurations are crucial for privacy and data protection.

**Advanced Security Options**

Google Cloud Storage offers additional security features:

* **Encryption:** Use Google's default encryption or manage your own encryption keys for maximum control. 🔑
* **Retention Rules:** Specify how long objects should be kept in the bucket before deletion. 🗓️

These features ensure your storage meets your security and compliance needs.

With these tools, you can develop a cost-effective, secure, and reliable storage infrastructure. Keep exploring and learning to maximize Google Cloud Storage in your projects! 🚀

## Understanding BigTable: Your Key to Big Data Management 🗝️🗄️

The world of databases is vast. Finding the right solution requires understanding your application's specific needs. BigTable, Google's NoSQL database service, excels at handling big data efficiently.  Understanding its workings and advantages will help you optimize services and prepare for rapid data growth.

**SQL vs. NoSQL: Choosing the Right Approach**

* **SQL Databases (Relational):**

SQL databases use a structured schema with tables made up of columns and rows. Every row must have a value in each column, ensuring data consistency and structure.

**Key Features:** Rigid schema, suitable for controlled growth, ideal for ACID transactions.

* **NoSQL Databases:**

NoSQL databases offer flexibility, agility, and scalability without the constraints of a structured schema. Store data in tables or documents, filling only necessary columns.

**When to Consider NoSQL:**  Large data volumes, unpredictable user growth, need for seamless scalability.

**Google Cloud BigTable:  A Fully Managed Solution**

BigTable is a fully managed service, meaning Google handles installation, configuration, and maintenance.

* **Key Benefits:** Handles massive data, low-latency processing, seamless scalability.

**Key Features of BigTable:**

* **Efficient Processing:** Stores vast amounts of data in a key-value format for fast read/write operations. 
* **Dynamic Resizing:** Scales seamlessly without downtime, ideal for mission-critical applications.
* **Automated Replication:** Data written once is automatically replicated for high availability.

**Integrating BigTable with Your Applications**

BigTable provides a robust ecosystem for data interaction:

* **Application API:** Use the HBase REST service layer for read/write operations.
* **Streaming:** Real-time data streaming using frameworks like Dataflow, Spark Streaming, or Apache Storm.
* **Batch Processing:**  Use tools like Hadoop, MapReduce, and Apache Spark for efficient large-scale data handling.


**How BigTable Stores Information**

BigTable uses a table approach with column families and unique qualifiers within each family. Cells can hold multiple records identified by unique timestamps. This design creates a compressed, agile database without wasted space for empty fields.

* **Data Structure:** Related column groups (column families), unique row identifiers (route keys), timestamped cell intersections for unique records.

Understanding BigTable, its differences from SQL, and its capabilities equips you to make informed decisions about using this powerful tool.  Choosing the right database is crucial for project success and sustainable growth.  Keep learning and exploring the world of data! 🚀

## [Creating a BigTable Database in Google Cloud: A Step-by-Step Guide](https://cloud.google.com/bigtable/docs/create-instance-write-data-cbt-cli?_ga=2.193490541.-1349049076.1674041542&_gac=1.122988281.1674041542.CjwKCAiAzp6eBhByEiwA_gGq5B1RB_gaHdEzPQWF7BOIKA6xt1JBgl0GGAEWdVBH6Tugg6LLM86iQxoClfgQAvD_BwE&cloudshell=false) 🚀

BigTable is a powerful tool in Google Cloud that allows you to efficiently store and manage massive amounts of data. This tutorial will guide you through creating your own BigTable database and interacting with it. This process is crucial for utilizing the kind of data infrastructure employed by large-scale companies like Google.

**Setting up a BigTable Instance**

First, you need to access the Google Cloud Console. Once there:

1. Go to the main menu. Select the "Databases" section and choose "BigTable." 🗄️
2. Click "Create Instance" and fill in the requested information.  You can name your instance something like "quickstart-instance."
3. An ID will be assigned automatically; let the system handle this.  ✅
4. Select the disk type; we recommend SSD for better performance. 💾
5. Choose a region and zone. A good example is "US East 1" (South Carolina) and zone "c." 🌎
6. Define the number of nodes. For testing, one node is usually sufficient. Then, click "Create."
7. Once the instance is created, you'll see a green icon indicating it's ready to use.🟢

**Interacting with BigTable using Cloud Shell**

With your instance ready, let's interact with it through Cloud Shell using the `cbt` command (short for Cloud BigTable).

**Running from gsutil CLI**

  ```bash
  cbt createinstance quick-start-instance "quick-start-instance" quickstart-instance-c1 us-east1-c 1 SSD
  ```
Where
* `quick-start-instance` the id
* `"quick-start-instance"` the instance name
* `quickstart-instance-c1` cluster's id
* `us-east1-c` region
* `1` node's numnber
* `SSD` Disk kind

**[cbt - documentation](https://cloud.google.com/bigtable/docs/cbt-reference)**

**Initial Cloud Shell Setup:**

1. Open Cloud Shell from your console. 🐚
2. To associate the instance with your project, use a `.cbtrc` file and put in your project ID using the appropriate command.
  ```bash
  echo project = `gcloud config get-value project` > ~/.cbtrc
  ```
3. Indicate that you'll be working with the "quickstart-instance" using the following configuration code. This tells `cbt` which instance to target.
  ```bash
  echo instance = my-instance >> ~/.cbtrc
  ```

**Creating and Managing Tables in BigTable**

* **Creating a table:**
  ```bash
  cbt create table myTable
  ```

* **Authorize Cloud Shell** to interact with the BigTable API and confirm table creation by listing the tables:

  ```bash
  cbt ls
  ```
  You should see "myTable" in your database.

* **Adding a column family:** Column families group related columns together.
  ```bash
  cbt create family myTable CF1 
  ```

* **Confirm creation** by listing families:
  ```bash
  cbt ls myTable
  ```

* **Adding data to your table:** Insert data into cells using:
  ```bash
  cbt set myTable r1 CF1:c1 "test value" 
  ```
  This creates a qualifier (`c1`) within the column family (`CF1`) and stores a test value.

* **Reading data from your table:** To visualize the structure, read the table with:
  ```bash
  cbt read myTable
  ```
  You'll see the inserted records and their timestamps, which make them unique within the database.

* **Delete the whole table:**
  ```bash
  cbt deleteinstance platzi-app-instance
  ```
  DO NOT FORGET TO DELETE ALL RESOURCES CREATED

**Why Use BigTable?**

BigTable stands out for its robustness and ability to handle massive amounts of distributed data. It's ideal for sectors requiring high scalability and efficiency, such as search engines, big data analytics, and real-time applications.

Keep exploring BigTable, create more complex structures, and discover how this platform can optimize your applications! Every step in your learning journey brings you closer to building efficient and scalable systems. 🌱

## SQL Databases for Sensitive Operations: Ensuring Data Integrity and Accuracy 🛡️

SQL databases are essential when information integrity and accuracy are paramount.  Think about transferring money between bank accounts 🏦—that's where transactional databases like SQL shine, handling complex operations while ensuring consistency and security.

**ACID Properties of SQL Databases: The Cornerstones of Reliable Transactions**

The ACID acronym summarizes the four critical properties of secure and reliable SQL database transactions:

* **Atomicity:** All operations in a transaction are treated as a single unit. If one fails, the entire transaction is rolled back, preventing incomplete money transfers or other inconsistencies. 🔄
* **Consistency:** Transactions maintain the database's integrity, ensuring data is always in a valid state.  Transferred money is accurately reflected in both accounts. 
* **Isolation:** Transactions operate independently, as if they were the only ones happening. This prevents interference between concurrent transactions, like two users accidentally modifying the same account simultaneously. 🚧
* **Durability:** Once a transaction is complete, it's permanent, even in case of system failures.  Your data is safe and sound. 💾

[**Google Cloud SQL: Managed SQL in the Cloud ☁️**](https://cloud.google.com/sql?hl=en)

Google Cloud SQL is a fully managed service that simplifies the administration and scaling of SQL databases.  You don't need to manage the underlying infrastructure—Google takes care of that!  Cloud SQL is ideal for migrating existing SQL-based applications to the cloud, preserving essential transactional properties.

**Key Features of Google Cloud SQL:**

* **Fully Managed:**  No more manual configurations or tuning! Focus on your application, not database administration. ⚙️
* **Vertical Scalability:** Based on virtual machines, Cloud SQL lets you upgrade to a more powerful VM for increased resources.⬆️
* **Automatic Backup and Recovery:** Schedule backups manually or automatically for peace of mind. 💾
* **High Availability:** Configure multi-zone deployments for continuous database accessibility, even during failures. 🌎🌎🌎
* **Easy Integration:**  Seamlessly integrates with other Google Cloud services like App Engine and Compute Engine.  You can even access it from your local machine. 💻
* **Reliability and Easy Migration:** Migrate data from traditional environments to the cloud using tools like Database Migration Service. 🔄

**Why Choose Google Cloud SQL?**

Google Cloud SQL provides the technology and support to maintain secure and efficient SQL databases without the management overhead. If you handle sensitive data like financial transactions, this service offers peace of mind and rock-solid reliability.  Take the leap and discover how Google Cloud SQL can empower your digital transformation in the cloud! 🚀

## Cloud SQL vs. Cloud Spanner: Choosing the Right Database for Your Needs

When choosing between Cloud SQL and Cloud Spanner, understanding their differences is key.  Consider an application with global users, like YouTube or Spotify 🌎—low latency is essential for quick responses.

* **Cloud SQL:** Effective for users in a single region or when minor delays aren't critical. A more economical and simpler option for local or regional needs. 💰
* **Cloud Spanner:** Ideal when global consistency is required for users in multiple regions. Offers global scalability but is more expensive. Provides fast, reliable service worldwide. 🌍

Both are SQL databases, but the best choice depends on the scale and geographical distribution of your users.

## [Cloud Spanner](https://cloud.google.com/spanner?hl=en): Globally Distributed SQL Database 🌎🗄️

Cloud Spanner is a globally managed SQL database, perfect for businesses needing high availability and low latency.

**Key Features of Cloud Spanner:**

* **Horizontal Scalability:** Easily scale your database without worrying about underlying infrastructure. 
* **Five Nines Availability (99.999%):** Minimal downtime for mission-critical applications.
* **Automatic Sharding:** The database adapts to data volume and requests, optimizing performance.

**Creating a Cloud Spanner Instance:**

1. Go to the "Databases" menu in the Google Cloud Console and select "Spanner."
2. Create a new instance, give it a name, and choose a regional or multi-region configuration.
3. Create a database within the instance.

**Creating an Instance from the gcloud CLI:**

You can create a Cloud Spanner instance using the `gcloud` command-line tool.  For example, to create a regional instance named `example-db` in the `us-central1` region with one node:

```bash
gcloud spanner instances create example-db --config=regional-us-central1 --nodes=1
```

**Managing Databases in Cloud Spanner**

* **Creating Tables and Schemas:**

Within a Cloud Spanner database, you can create tables and define schemas:

```sql
CREATE TABLE Singers (
    SingerId INT64 NOT NULL,
    FirstName STRING(1024),
    LastName STRING(1024),
    SingerInfo STRING(MAX),
    BornDate DATE
) PRIMARY KEY (SingerId);
```

**Creating a Database and Schema from the gcloud CLI:**

To create a database named `example-db-db` in your `example-db` instance:

```bash
gcloud spanner databases create example-db-db --instance=example-db
```

Then, to create the `Singers` table:

```bash
gcloud spanner databases ddl update example-db-db \
--instance=example-db \
--ddl='CREATE TABLE Singers ( 
        SingerId INT64 NOT NULL, 
        FirstName STRING(1024), 
        LastName STRING(1024), 
        SingerInfo BYTES(MAX) 
        ) PRIMARY KEY (SingerId)'
```



* **Inserting, Updating, and Deleting Data:** Use standard SQL commands or the `gcloud` CLI:

    * **Insert (gcloud):**

    ```bash
    gcloud spanner rows insert --database=example-db-db \  
    --instance=example-db \
    --table=Singers \  
    --data=SingerId=1,FirstName=Marc,LastName=Richards
    ```

    * **Insert (SQL):**
        ```sql
        INSERT INTO Singers (SingerId, FirstName, LastName)
        VALUES (1, "Mark", "Richards");
        ```

* **Updating Data:** Let's say you want to update the `FirstName` of the singer with `SingerId = 1` to "Will":
      
    * **gcloud:**
        ```bash
        gcloud spanner rows update --table=Singers --database=example-db-db --instance=example-db \
        --data="SingerId=1,FirstName=Will" 
        ```
      
    * **SQL:**
        ```sql
        UPDATE Singers SET FirstName = 'Will' WHERE SingerId = 1;
        ```

* **Deleting Data:** Let's say you want to delete the singer with `SingerId = 2`:

    * **gcloud:**
        ```bash
        gcloud spanner rows delete --table=Singers --database=example-db-db \
        --instance=example-db --keys=2
        ```
    
    * **SQL:**
        ```sql
        DELETE FROM Singers WHERE SingerId = 2;
        ```

* **Reading Data:** Query your data using SQL or the `gcloud` CLI:

    * **Read (gcloud):**
        ```bash
        gcloud spanner databases execute-sql example-db-db \ 
        --instance=example-db \
        --sql='SELECT * FROM Singers'
        ```
    * **Read (SQL):**
        ```sql
        SELECT * FROM Singers;
        ```


**Tips for Using Cloud Spanner:**

* Start with scripts for managing large datasets. 📜
* Leverage automatic sharding for easier scaling.
* Ensure unique identifiers (like `SingerId`) maintain referential integrity. 🔑

As you gain experience, you'll become more efficient at managing large databases with Cloud Spanner. Keep exploring! 🚀

---
### [UP](https://github.com/DLesmes/GCP/blob/main/content/storage_on_gcp.md#home)
