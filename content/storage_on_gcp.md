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

**[cbt - documentation](https://cloud.google.com/bigtable/docs/cbt-reference)**

**Initial Cloud Shell Setup:**

1. Open Cloud Shell from your console. 🐚
2. To associate the instance with your project, use a `.cbtrc` file and put in your project ID using the appropriate command.
3. Indicate that you'll be working with the "quickstart-instance" using the following configuration code. This tells `cbt` which instance to target.

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

---
### [UP](https://github.com/DLesmes/GCP/blob/main/content/storage_on_gcp.md#home)
