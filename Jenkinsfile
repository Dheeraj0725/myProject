pipeline {
  agent { label 'linux' }
  tools {
    maven 'M3'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/Dheeraj0725/myProject.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        bat 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        bat 'mvn package'
      }
    }
  }
}
