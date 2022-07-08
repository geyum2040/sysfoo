pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package -DskipTests'
      }
    }

    stage('error') {
      steps {
        archiveArtifacts '**/target/*.war'
      }
    }

  }
  tools {
    maven 'M2_HOME'
  }
}