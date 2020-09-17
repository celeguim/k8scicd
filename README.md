### Create A CI/CD Pipeline With Kubernetes And Jenkins

### Thanks to 
- <https://www.magalix.com/blog/create-a-ci/cd-pipeline-with-kubernetes-and-jenkins>
- <https://github.com/magalixcorp/k8scicd>

### Install tools
- Install Java
    - sudo yum install java-1.8.0-openjdk-devel

- Enable Jenkins Repo
    - curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo

- Add repo to the system
    - sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

- Install Jenkins
    - sudo yum install jenkins

- Start and Enable 
    - sudo systemctl start jenkins
    - sudo systemctl enable jenkins
    - sudo systemctl status jenkins

- Adjust Firewall
    - sudo firewall-cmd --permanent --zone=public --add-port=8080/tcp
    - sudo firewall-cmd --reload

- Install docker repo
    - sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

- Install docker engine
    - sudo yum install docker-ce docker-ce-cli containerd.io

- Start and enable docker
    - sudo systemctl start docker
    - sudo systemctl enable docker
    - sudo systemctl status docker

- Install kubernetes client  

```
cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF

yum install kubect
```


- Install Python 3, Ansible, and the openshift module:  

```
sudo yum install -y python3 
sudo yum install -y python3-pip
sudo pip3 install ansible 
sudo pip3 install openshift
sudo pip3 install kubernetes
```

- Install jenkins and docker (if needed)

```
ansible-galaxy install geerlingguy.jenkins
ansible-galaxy install geerlingguy.docker
```

