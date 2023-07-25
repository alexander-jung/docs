---
title: Manage Databases with Terraform
summary: Learn how to manage databases using the CockroachDB Cloud Terraform provider.
toc: true
docs_area: manage
---

[Terraform](https://terraform.io) is an infrastructure-as-code provisioning tool that uses configuration files to define application and network resources. You can manage SQL databases in CockroachDB Cloud by using the [CockroachDB Cloud Terraform provider](https://registry.terraform.io/providers/cockroachdb/cockroach) in your Terraform configuration files.

This page shows you how to manage your databases using the CockroachDB Cloud Terraform provider.

## Before you begin

Before you start this tutorial, you must have [the CockroachBDCloud Terraform provider](https://learn.hashicorp.com/tutorials/terraform/install-cli) set up. Follow the tutorial to [Provision a Cluster with Terraform](provision-a-cluster-with-terraform.html) to start using Terraform with a new cluster.

## Create a new database

1. Add the following snippet of code to your `main.tf` file:

    ~~~
    resource "cockroach_database" "<resource-name>" {
      name       = "<database-name>"
      cluster_id = cockroach_cluster.<cluster-name>.id
    }
    ~~~
    
    Where `<resource-name>` is the name of the database resource that will be created, `<database-name>` is the name of the database you want to create, and `<cluster-name>` is the cluster's resource name.
    
1. Run the `terraform apply` command in your terminal.
    
    You will be prompted to enter the value `yes` to apply the changes.

## Change the name of a database

To change the name of a database, you can edit the database's `name` variable in your `main.tf` file. The following snippet will rename the database [created](#create-a-new-database) in the previous example:

~~~
resource "cockroach_database" "<resource-name>" {
  name       = "<database-new-name>"
  cluster_id = cockroach_cluster.<cluster-name>.id
}
~~~

Run the `terraform apply` command in your terminal to apply the changes.

## Delete a database

To delete a database, you can delete its corresponding resource from your `main.tf` file and run the `terraform apply` command in your terminal to apply the changes.

Deleting a database will also permanently delete all data within the database.

## Learn more

- See the [CockroachDB Cloud Terraform provider reference docs](https://registry.terraform.io/providers/cockroachdb/cockroach/latest/docs) for detailed information on the resources you can manage using Terraform.
- Read about how to [provision a cluster with Terraform](provision-a-cluster-with-terraform.html).
- Read about how to [export logs and metrics with Terraform](manage-database-terraform.html).