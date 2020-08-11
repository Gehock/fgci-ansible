# admin-test1.cs.aalto.fi setup

```shell
# git clone
cd fgci-ansible
vim hosts
ssh-keygen
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
touch ssh-config

ansible-galaxy install -r requirements.yml
ansible-playbook install.yml \
    --tags=fgci-install,flowdock \
    --diff -e flowdock_from_address=pullReqs@{{siteDomain}}

ansible-playbook admin_ohpc.yml -C
```
