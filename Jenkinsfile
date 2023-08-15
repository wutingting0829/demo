pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/wutingting0829/demo', branch: 'main')
      }
    }

    stage('error') {
      parallel {
        stage('error') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-End Unit Test') {
          steps {
            sh './mvnw clean install  && ./mvnw spring-boot:run'
          }
        }

      }
    }

  }
}