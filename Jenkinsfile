pipeline{
    agent any
    stages{        
        stage('Dev Deploy'){
            when{
                branch 'Dev'
            }
            steps{
              echo 'Deploy to Dev'
            }
        }        
    }
    stages{        
        stage('UAT Deploy'){
            when{
                branch 'UAT'
            }
            steps{
              echo 'Deploy to UAT'
            }
        }        
    }
    stages{        
        stage('Prod Deploy'){
            when{
                branch 'Prod'
            }
            steps{
              echo 'Deploy to Prod'
            }
        }        
    }
}
