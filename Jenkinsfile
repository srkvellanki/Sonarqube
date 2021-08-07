pipeline {
  agent any
  stages {
    stage('Dev Deploy') {
      when {
        branch 'Dev'
      }
      steps {
        echo 'Deploy to Dev'
      }
    }
    stage('UAT Deploy') {
      when {
        branch 'UAT'
      }
      steps {
        echo 'Deploy to UAT'
      }
    }
    stage('Prod Deploy') {
      when {
        branch 'Prod'
      }
      steps {
        echo 'Deploy to Prod'
      }
    }
  }
}
