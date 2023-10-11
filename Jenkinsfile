pipeline {
    agent any

    
    stages {
        stage('Build') {
            steps {
               sh'''
               mvn clean install
               '''
         } 
        }

          stage('Deploy') {
                steps {
                sh'''
                   scp /mnt/Project/game-of-life/gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.80/webapps/
                '''
     
             }
         }
     }
}
