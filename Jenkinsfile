pipeline 
{
    agent any {
	node {
			label 'built-in'
			customworkspace '/home/ec2-user'
		}
			}
    stages {
        stage('CheckoutGit') {
            steps {
                // Get code from a GitHub repository
                sh '''
                git clone https://github.com/wakaleo/game-of-life.git
                '''
				}
			}
        stage('Build') {
            steps {
                // maven install
                sh '''
                mvn clean install
                   '''
				}
			}
        stage('Deploy') {
            steps {
                // Deploying war to tomcat
                sh '''
                cp /home/ec2-user/Game of life/gameoflife-web/target/gameoflife.war /mnt/apache-tomcat-9.0.80/webapps/
                '''
				}
			}
        }
}
