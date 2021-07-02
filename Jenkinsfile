pipeline {
    agent any

    stages {
        stage ('BuildStage') {

            steps {
                fileExists 'pom.xml'
                
                    sh 'mvn compile'
                }
            }
        

        stage ('Testing Stage') {

            steps {
      
                    sh 'mvn clean test'
                }
            }
        


        stage ('Deployment Stage') {
            steps {
               
                    sh 'mvn package'
                }
            }
        
            
          stage ('Archive Stage') {
            steps {
             
                   archiveArtifacts '**/target/myweb-0.0.2-SNAPSHOT.war'
                }
            }   
             stage ('cp Stage') {
            steps {
             
                   sh "sudo cp -rf '**/target/myweb-0.0.2-SNAPSHOT.war' /root/jenkins/apache-tomcat-9.0.48/webapps"
                }
            }   
       
    }
}
