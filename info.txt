# docker-setup
Before create role needed to install ansible_collection on the same directory with ansible role playbook.yml
use thi commands:
mkdir ansible_collections
cd ansible_collections
ansible-galaxy collection download community.docker
find . -name "community-docker-*.tar.gz"
   You should see output like:
    ./collections/community-docker-4.6.1.tar.gz
ansible-galaxy collection install ./collections/community-docker-4.6.1.tar.gz
ansible-galaxy collection list | grep community.docker
     Expected output: community.docker  4.6.1
 .
├── ansible_collections
│   └── collections
│       ├── community-docker-4.6.1.tar.gz
│       ├── community-library_inventory_filtering_v1-1.1.1.tar.gz
│       └── requirements.yml
├── inventory
├── playbook.yml
└── roles
    └── docker_swarm_webapp
        ├── defaults
        │   └── main.yml
        ├── files
        │   └── Dockerfile
        └── tasks
            └── main.yml    