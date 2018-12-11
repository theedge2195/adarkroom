pipeline {
  agent any
  stages {
    stage('') {
      steps {
        sh '''#!/bin/bash
cd /
sudo su
yum install docker -y
service docker start
chkconfig docker on
docker run -dit --name adarkroom -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4'''
      }
    }
  }
}