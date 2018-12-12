pipeline {
  agent any
  stages {
    stage('Staging') {
      steps {
        sh '''#!/bin/bash
cd ~
sudo su
sudo docker stop adarkroom
sudo docker rm adarkroom
sudo docker build -t haydencardwell/adarkroom .
sudo docker run --restart always --name adarkroom -p 80:80 -d haydencardwell/adarkroom
'''
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