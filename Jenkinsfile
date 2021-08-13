pipeline{
    agent any    
    stages{        
        stage('Maven Build'){
            steps{
              sh  "mvn clean package"
            }
        } 
        stage('Upload to Nexus'){
            steps{
              nexusArtifactUploader artifacts: 
              [[artifactId: 'maven-project', classifier: '', file: 'maven-project-1.0-SNAPSHOT.war', type: 'war']], 
              credentialsId: 'Nexus-Credentials', 
              groupId: 'com.example.maven-project', 
              nexusUrl: '172.31.40.117:8081',                   
              nexusVersion: 'nexus3', 
              protocol: 'http', 
              repository: 'nexus-maven2-snapshot', 
              version: '1.0-SNAPSHOT'
            }
        } 
        stage('dev-deploy'){
            when{
                branch "Dev"
            }
            steps{
              echo  "deploy to Dev"
            }
        } 
        stage('Master-deploy'){
            when{
                branch "Master"
            }
            steps{
              echo  "deploy to Master"
            }
        } 
    }
}
