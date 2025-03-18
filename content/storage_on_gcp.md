### [Home](https://github.com/DLesmes/GCP/blob/main/README.md#google-cloud-tools)
---

# Storage on GCP
## Services comparisson
![](https://static.platzi.com/media/user_upload/Screenshot_26-ff620129-2ba2-4c0f-aa8e-78aa6f91cfab.jpg)

## Storage Decision Tree
![](https://1.bp.blogspot.com/-H4a0slANRLg/XXFGsDshuKI/AAAAAAAAAAU/Ov1pyV1IOqQJvSfTJy50eL6dGCrCBHk-wCLcBGAs/s1600/storageoptions.jpg)

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


**Why Use BigTable?**

BigTable stands out for its robustness and ability to handle massive amounts of distributed data. It's ideal for sectors requiring high scalability and efficiency, such as search engines, big data analytics, and real-time applications.

Keep exploring BigTable, create more complex structures, and discover how this platform can optimize your applications! Every step in your learning journey brings you closer to building efficient and scalable systems. 🌱

---
### [UP](https://github.com/DLesmes/GCP/blob/main/content/storage_on_gcp.md#home)
