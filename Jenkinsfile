pipeline {
  agent any
  tools {
    maven 'MavenVer3'
  }
  stages {
    stage('maven build') {
      sh 'mvn clean package'
    }
    stage('Upload to Nexus') {
      steps {
        nexusArtifactUploader artifacts: [
            [artifactId: 'maven-project', classifier: '', file: 'maven-project-1.0-SNAPSHOT.war', type: 'war']
          ],
          credentialsId: 'Nexus-Credentials',
          groupId: 'com.example.maven-project',
          nexusUrl: '172.31.40.117:8081',
          nexusVersion: 'nexus3',
          protocol: 'http',
          repository: 'nexus-maven2-snapshot',
          version: '1.0-SNAPSHOT'
      }
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
