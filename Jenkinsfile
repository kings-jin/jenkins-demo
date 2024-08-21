pipeline {
  agent {
    docker {
      args ' -v /root/repo:/root/.m2'
      image 'maven:3.9.9-eclipse-temurin-21-alpine'
    }

  }
  stages {
    stage('pull code') {
      steps {
        git(url: 'https://gitee.com/jzywjj/jenkins-demo.git', branch: 'main')
      }
    }

    stage('buid') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }

  }
}