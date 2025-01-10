# Project

## Requirements

- Docker
- Docker Compose
- Minikube
- Kubectl
- Git
  
### Check Requirements

```bash
docker --version            # Should be Docker 24.0.7 or higher
minikube version            # Should be Minikube v1.31.2 or higher
kubectl version --client    # Should be Kubernetes CLI v1.28.3 or higher
docker-compose --version    # Should be Docker Compose v2.23.0 or higher
git --version               # Should be Git 2.41.0 or higher
```

## Setup

### Retrieve the source code repository locally on your virtual machine with the command

```bash
git clone https://github.com/AlexiFa/DevOps-M2/Project.git
```

### Launch Jenkins

```bash
sudo docker run -d -p 8080:8080 -p 50000:50000 --name jenkins --restart unless-stopped jenkins/jenkins:lts-jdk-17
```

Get the admin password

```bash
sudo docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

### Install Jenkins Plugins <!-- TODO : check if it is enough -->

- Docker Pipeline

### Create Jenkins Agent (and launch it) <!-- TODO -->


### Create Credentials <!-- TODO -->

Navigate to Manage Jenkins > Credentials in the Jenkins interface.

Add two sets of credentials:

Git : https://github.com/AlexiFa/DevOps-M2/Project.git
username: bash```ST2DCE```
password: bash```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```

Docker Hub:
Username: bash```efrei2023```
Password: bash```efrei2023```

### Create a network for docker infrastructure:

```bash
docker network create --driver bridge efrei
```



### Create Jenkins Pipeline <!-- TODO : add arrows to the screenshots -->

![Jenkins new item](screen/1-jenkins-new-item.png)

![Jenkins new pipeline](screen/2-jenkins-new-pipeline.png)

![Jenkins pipeline configuration](screen/3-jenkins-configure-pipeline.png)

then, you can build the pipeline from the jenkins dashboard and at the end you will see the container running

```bash
sudo docker ps
```

And you will see the API running at `http://localhost:8081`

`http://localhost:8081/whoami` will return our names
