pipeline {
  agent {
    docker {
      image 'maven:3.9.9-eclipse-temurin-21-alpine'
      args '-v /root/repo:/root/.m2'
    }

  }
  stages {
    stage('pull code') {
      steps {
        git(url: 'https://gitee.com/jzywjj/jenkins-demo.git', branch: 'main', poll: true)
      }
    }

    stage('buid') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }

  }
}