# Azure
---
## Azure Basic Setup for Begineers

When we start a new project, it is important to setup the layers for better management. 
### Subscription
Subscription is the top layer in Azure Portal, It will give the user a default subscription after the account creation. The Purpose of Setup differnet subscriptions to sperate different projects based on different logics and resources. 

### Resource Group
The layer after Subscription. The purpose of creating different resource groups is to create a more detailed claffication. 
For example we have Different versions within one project with different resources like database, VM

### Storage Account

Data Lake. Create a storage account to store up to 500TB of data in the cloud. 

make sure the storgae accounts for one project under the same resource group. 

Process: Data are stored in storage accounts first and then be able to move to other data warehouse like Snowflake. 

Difference between ADLS(File based storage) and Storage account: Use ADLS when we only have files; Storage account has container and blobs; 


### Azure Active Directory(AAD)
* Create and manage the Users
* Role Assignment
### Create Azure SQL DataBase
#### Create SQL server
* Admin Setup in AAD

#### SSMS(SQL Server Management Studio)
##### Login Information
* Server Name: *.database.windows.net
* Autherication with User Name: username@email.onmicrosoft.com and Password(From User creation in AAD)
##### Attention
* Need authenicate the user in Azure AAD
* Allow all public network
* Add Local IP address into the rule







## Azure ADF
### Introduction
### Linked Services
* SSMS; Make sure to grant the access to ADF
  ```SQL
  create user rpanadf FROM EXTERNAL PROVIDER;
  alter role db_owner add member rpanadf;
  ```
* SnowFlake; To get the host; 
  ```Sql
  select SYSTEM$ALLOWLIST()
  ```


## Azure ADF Pipelines
1. Copy Data from Azure SQL DataBase to SnowFlake
   * []
2. Copy Files from Azure blob Storage Account to Azure SQL DataBase with Activity: **Copy Data**
3. Copy files from Azure blob Storage Account to Azure SQL DataBase with Activity: **Get MetaData**, **ForEach**, **Copy Data**
   
## Azure DataBricks
