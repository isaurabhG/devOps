pipeline{
    agent any
    stages{
        stage("code-pull"){
            steps{
                git 'https://github.com/shashirajraja/Train-Ticket-Reservation-System.git'
            }
        } 
        stage("build"){
            steps{
                echo "====++++code-is-building++++===="
                sh '''mvn clean package'''
            }    
        }
        stage("deploy"){
            steps{
               deploy adapters: [tomcat9(credentialsId: 'tomcat-id', path: '', url: 'http://54.64.70.120:8080/')], contextPath: '/', war: '**/*.war'
            }    
        }
    }
}
