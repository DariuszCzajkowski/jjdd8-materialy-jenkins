pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
  }
  stages {
    stage('Testing/Shell Script') {
      steps {
        sh 'mvn clean'
        sh 'mvn --projects biojava-alignment test'
      }
    }
    stage('Whatever') {
      steps {
        sh 'echo "hello from Jenkins"'
      }
    }
  }
      post {
        
  always {
    junit 'biojava-alignment/target/surefire-reports/**/*.xml'
  }
      }
  }
