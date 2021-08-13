pipeline{
    agent any
    tools{
        maven 'maven3'
    }
    stages{        
        stage('Maven Build'){
            steps{
              sh  "mvn clean package"
            }
        } 
        stage('Upload to Nexus'){
            steps{
              sh  "mvn clean package"
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
    }
}
