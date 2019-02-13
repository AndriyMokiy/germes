pipeline {
  agent any
  stages {
    stage('unit test') {
      steps {
        withEnv(overrides: ["PATH+EXTRA=/usr/local/bin"]) {
          sh 'mvn clean test'
        }

      }
    }
    stage('integration test') {
      steps {
        sh 'echo \'Integration tests are running\''
      }
    }
    stage('Smoke UI test') {
      steps {
        build(job: 'Smoke UI Test', propagate: true, wait: true)
      }
    }
  }
}