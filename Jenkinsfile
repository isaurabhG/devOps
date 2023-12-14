pipeline{
    agent any
    stages{
        stage("code-pull"){
            steps{
                git 'https://github.com/isaurabhG/claim-microservice.git'
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
               deploy adapters: [tomcat9(credentialsId: 'tomcat-id', path: '', url: 'http://35.73.241.192:8080')], contextPath: '/', war: '**/*.war'
            }    
        }
    }
}
