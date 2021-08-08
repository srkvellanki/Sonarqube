pipeline {
  agent any
  tools{
    maven 'MavenVer3'
  }
  stages {
    stage('maven build'){
      sh 'mvn clean package'
    }
    stage('upload to nexus'){
      sh 'mvn clean package'
    }
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
