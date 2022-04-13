pipeline {
  agent any
  tools {
    maven 'M2_HOME'
  }
  stages {
    stage('build'){
      steps {
        sh 'mvn clean'
        sh 'mvn install'
        sh 'mvn package'
        sleep 2
      }
    }
    stage('test'){
      steps {
        echo "test steps" 
        sh 'mvn test'
        sleep 2
      }
    }
    stage('deploy'){
      steps {
        echo "deploy steps" 
        sleep 2
      }
    }
    stage('docker'){
      steps {
        echo "image" 
        sleep 2
      }
    }
  }
}
