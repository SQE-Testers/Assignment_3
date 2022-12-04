
# Reliability Magento

This section describes the reliability , scalability 
and cloud usage of Magento.Magento uses AWS cloud services.
Magento cloud provides following benefits:

- Rapid Development
- Continuous Deployment
- Customizable Environment
- High Scalability
- Enhanced Security

### High Scalability:
When it comes to scalability , Magento becomes highly
scalable because of cloud. Because of cloud you can
add alot of audience and cloud supports advanced 
scalability features such as order archiving, 
multiple master servers, scalable 
backend product management, and MySQL 
customer support. 
Some of the Magento scaling tasks include:

- Installing new services
- Upscale & downscale resources
- Server provisioning to avoid resource wastage
- Auto Scaling solutions
- Optimizing usage for low costs

### Multiple Master Server
Adobe Commerce offers number of scalability advantages, including the ability to use three separate master databases for different functional areas of the Magento application.

Checkout, orders, and product data can all each use a separate master databases that you can optionally replicate. This separation independently scales load from website checkouts, order management activities, website browsing, and merchandising activities, depending on your needs. These changes provide considerable flexibility in how the database tier can be scaled.Multi-master replication is a method of database replication which allows data to be stored by a group of computers, and updated by any member of the group. All members are responsive to client data queries

### Continuous Data Backup

Magento do continous data backup for it users.
Data can be lost due to human error or a cyber attack
Some time hackers black mail us by getting our sensitive
data.The backup tasks can be managed by the Magento support staff.
Routine backups are done when you use the Magento hosting support. 
For your Magento system and databases, they create backups.
In any unavoidable circumstances data can be retrieved quickly.

### Commands
```bash
bin/magento config:set system/backup/functionality_enabled 1
```


### Load Balancing
Magento Support team provides the services of Load
Balancing. With this service they take care of all the
aspects through which a website can become unaccessible.

Magento do it by : 

- Operating system patches
- Incremental and full backups
- Continous support on Application level

### References
- [Magento Cloud Architecture ](https://devdocs.magento.com/cloud/architecture/cloud-architecture.html?itm_source=devdocs&itm_medium=search_page&itm_campaign=federated_search&itm_term=Reliability)
-[Backup Documentation](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-backup.html#instgde-cli-uninst-back-over)

