### Create A CI/CD Pipeline With Kubernetes And Jenkins

### Thanks to 
- <https://www.magalix.com/blog/create-a-ci/cd-pipeline-with-kubernetes-and-jenkins>
- <https://github.com/magalixcorp/k8scicd>

### Install tools
- Install Python 3, Ansible, and the openshift module:  

```
sudo apt update && sudo apt install -y python3 && sudo apt install -y python3-pip && sudo pip3 install ansible && sudo pip3 install openshift
```

- Install jenkins and docker (if needed)

```
ansible-galaxy install geerlingguy.jenkins
ansible-galaxy install geerlingguy.docker
```

