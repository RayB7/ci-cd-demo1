pipeline {
  agent any
  tools {
      go 'gotest'
  }
  environment {
      GO111MODULE='on'
  }
  
  stages {
    stage('Test') {
      steps {
        git 'https://github.com/RayB7/ci-cd-demo1.git'
        sh 'go test ./...'
      }
    }
    stage('Build') {
        steps {
        git 'https://github.com/RayB7/ci-cd-demo1.git'
        sh 'go build .'
        }
    }
    stage('Run') {
        steps {
            sh 'cd /var/lib/jenkins/workspace/test-jenkins && go-webapp-sample &'
        }
    }

  }
}
