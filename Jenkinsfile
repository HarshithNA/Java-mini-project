pipeline {
    agent any
    tools {
        jdk 'jdk17'
        maven 'maven3'
    }
    stages {
      stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/HarshithNA/Java-mini-project.git'
            }
        }
  stage('build') {
    steps {
      dir('sample-app') {
      sh 'mvn clean install'
      }
    }
  }
  stage('deploy') {
    steps {
      echo "this is deploy"
    }
  }

}
post {
  success {
    echo "job built successfully"
    archiveArtifacts artifacts: '**/target/*.war'
  }
  failure {
    echo "job built was a failure"
  }
}

}