pipeline {
    agent {
    node {
        label 'Built-In'
        customWorkspace '/home/ec2-user/12/game-of-life/'
            }
			}
    stages {
      		stage('Build') {
            steps {
                sh '''
                mvn clean install
                '''
            }
        }
		stage('Deploy') {
            steps {
                sh '''
                cp /home/ec2-user/12/game-of-life/gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.80/webapps/
                '''
            }
        }
    }
}
