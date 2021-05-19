pipeline {
  agent any
  stages {
    stage('Instalar Docker') {
      steps {
        sh '''#!/bin/sh
sudo yum update -y
sudo yum install -y docker
sudo service docker start
sudo usermod -a -G docker ec2-user
sudo chkconfig docker on
sudo yum install -y git'''
      }
    }

    stage('Instalar Docker-Compose') {
      steps {
        sh '''#!/bin/sh
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version'''
      }
    }

  }
}