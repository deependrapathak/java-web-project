pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'dbe1a7ed-5f5e-4ead-9bc6-d22f249cf755', path: '', 
                url: 'http://ec2-54-221-133-21.compute-1.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
