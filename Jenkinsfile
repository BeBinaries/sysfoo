pipeline {
  agent {
    docker {
      image 'maven:3.9.6-eclipse-temurin-17'
    }

  }
  stages {
    stage('build') {
      steps {
        echo 'compile maven app'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'test maven app'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'package maven app'
        sh 'mvn package -DskipTests'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
  tools {
    maven '3.6.3'
  }
}