def path = "~/workspace/FirstPipelineJob/webapp/target"

pipeline{
    agent any
    stages{        
        stage('Maven Build'){
            steps{
              sh 'mvn clean package'
            }
        }
        stage('Deploy to Tomcat Dev'){
            steps{
              sshagent(['tomcat-dev']) {
                // rename the war file.
                
                sh "mv ${path}/*.war ${path}/myweb.war"
                // copy war file to tomcat server
                sh "scp -o StrictHostKeyChecking=no ${path}/myweb.war ec2-user@3.144.47.123:/opt/tomcat8/webapps"
                // after copying stopt and start tomcat
                sh "ssh -tt ec2-user@3.144.47.123 sudo /opt/tomcat8/bin/shutdown.sh"
                sh "ssh -tt ec2-user@3.144.47.123 sudo /opt/tomcat8/bin/startup.sh" 
                //sh "ssh -tt ec2-user@3.144.47.123 sudo service tomcat8 restart"
               }
            }
        }
    }
}