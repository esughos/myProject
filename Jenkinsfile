pipeline {
  agent any
  tools {
    maven 'Maven 3.3.9'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/esughos/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
