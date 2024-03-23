### Ansible Playbook for Setting Up MongoDB Cluster (Debian & Redhat)

This Ansible playbook automates the setup of a MongoDB cluster on both Debian and Redhat family distributions. It provides flexibility in configuring the storage path and allows modifications to the MongoDB configuration based on specific requirements.

#### Structure

```plaintext
mongodb-ansible
├── files
│   └── mongodb-enterprise-4.2.repo
├── handlers
│   └── main.yml
├── tasks
│   ├── centOS.yaml
│   ├── debian.yml
│   └── main.yml
├── templates
│   ├── mongodc.j2          --------->For CentOS/Redhat
│   └── mongodd.j2          --------> For Ubuntu/Debian
└── vars
    └── main.yml
```

#### Usage

To run the playbook, follow these steps:

1. **Modify Hosts File**: Update the `hosts` file with the appropriate host information.

2. **Run the Command**:

   ```bash
   ansible-playbook -i ./hosts --private-key ~/.ssh/id_rsa -b mongo-db-main.yaml
   ```

   Note: Replace `mongo-db-main.yaml` with the name of your playbook file.

#### Configuration

- **Default Paths**:
  - For Debian family: `/opt/mongodb/data/`
  - For Redhat family: `/var/lib/mongo/`
  
  Modify the default paths in the variable file located in the `vars` directory if necessary.

- **Customization**:
  - Adjust the configuration file (in the `templates` directory) to meet specific requirements.

#### Authentication

Ensure the private key (`id_rsa`) is available for authentication.

This playbook simplifies the deployment of MongoDB clusters, providing a standardized and efficient solution for managing MongoDB installations across different Linux distributions. Contributions and feedback are welcome for further enhancements and optimizations.
