Ansible Playbook to Setup MongoDB Cluster For Both Debian & Redhat Family

This role includes the following structure. By default the dbstorage path for Debian family is /opt/mongodb/data/  &  for Redhat Family is /var/lib/mongo/ If needed we can modify the default path in Varibale file inside vars directory . Apart from this all the configuration is set to default. If needed feel free to modify the configuration file (in templates directory) as per the requirement.

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
│   ├── mongodc.j2			--------->For CentOS/Redhat
│   └── mongodd.j2			--------> For Ubuntu/Debian
└── vars
    └── main.yml



To run the playbook we just need to modify the hosts file and run the below command :-

ansible-playbook -i ./hosts  --private-key  ~/.ssh/id_rsa  -b mongo-db-main.yaml

Note:- Private key is the key for authentication 

