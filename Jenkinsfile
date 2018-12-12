pipeline {
  agent any
  stages {
    stage('Staging') {
      steps {
        sh '''#!/bin/bash
cd ~
sudo docker build -t haydencardwell/adarkroom .
sudo docker run -p 80:80 -d haydencardwell/adarkroom'''
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