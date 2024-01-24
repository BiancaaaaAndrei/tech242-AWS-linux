# Amazon Redshift

- Based on PostgreSQL, but not used for OLTP
- It's OLAP - online analytical processing (**analytics and data warehoursing**)
- Load data once every hour, not every second
- 10x better performance than other data warehouses, scales to PBs of data
- **Columnar** storage data (instead of row based)
- Does computations very quickly because of the MPP (Masively Parallel Query Executions) being highly available
- Pay as you go
- SQL interface
- BI tools to create dashboards on top of the data warehouse - build some visualisations for the boards on it

## Redshift Serverless

- **Serverless Operation**: Run analytics workloads without managing underlying infrastructure.
- **Pay for Usage**: Pay only for compute and storage used during analysis.
- **Easy Setup**: Enable Redshift Serverless on your account and connect the Redshift Query Editor or other tools to start writing queries.
- **Automated Provisioning**: Redshift Serverless automatically provisions and scales capacity based on the workload and queries.
- **Cost Efficiency**: Offers a cost-efficient alternative to traditional Redshift, especially for intermittent workloads.

![Redshift Serverless](<../../readme-images/Databases/Redshift serverless.jpeg>)