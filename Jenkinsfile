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
                deploy adapters: [tomcat7(credentialsId: 'f00d793b-d1e0-46be-8061-c0902899881b', path: '', 
                url: 'http://ec2-52-221-237-110.ap-southeast-1.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war' 
            }
        }
    }
}
