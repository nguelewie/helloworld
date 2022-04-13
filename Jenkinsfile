pipeline {
  agent any
  tools {
    maven 'M2_HOME'
  }
  environment {
    registry = "nguelewie/devops-ci"
    registryCredential = 'DockerRegistryID'
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
       script {
        docker.build registry + ":$BUILD_NUMBER"
          }
        }
     }
  }
}
