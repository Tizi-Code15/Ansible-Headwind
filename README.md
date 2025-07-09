# Headwind MDM deployment with ANsible 

This Ansible project automates the deployement of [headwind MDM](https://github.com/h-mdm/hmdm-server) using the offcial open-source repository.

> Note : This setup is designed specifically for the **official Headwind MDM source repository**.
>  The project must be **compiled from source** using Maven before being deployed.


---

## Features

- Clones and compiles Headwind MDM from the official GitHub repository.
- Sets up PostgreSQL and configures the required user/database.
- Configures Tomcat (default port changed from `8080` to `8082`).
- Deploys the compiled `launcher.war` into Tomcat.
- Allows custom configuration through `group_vars/all.yml`.
  

## configuration

Before deployment, edit the file:

Update the following variables to match your environment:

- **Directory paths**
- **Domain name** (`base_url`)
- **PostgreSQL credentials** (`postgres_user`, `postgres_password`, `postgres_db`)
- **Tomcat port** (`8082` by default, change if needed)

## Inventory Setup

Create a directory and file for your inventory:

```bash
mkdir inventory
touch inventory/hosts

[headwind_servers]
your-server-ip-or-hostname ansible_user=your_ssh_user
