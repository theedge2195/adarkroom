pipeline {
  agent any
  stages {
    stage('Staging') {
      steps {
        sh '''#!/bin/bash
cd ~
sudo su
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker build -t haydencardwell/adarkroom .
docker run -p 80:80 -d haydencardwell/adarkroom
docker stop $(docker ps -a -q)'''
      }
    }
    stage('Confirmation!') {
      steps {
        input 'Should we deploy?'
      }
    }
    stage('Production!') {
      steps {
        sh '''#!/bin/bash
pwd'''
      }
    }
  }
}