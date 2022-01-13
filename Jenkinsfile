pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh "mvn clean package"
            }
            
        }
        stage('deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '5dc8f832-55af-4c6b-9f7a-a6730e623e8c', 
                path: '', 
                url: 'http://ec2-35-161-14-135.us-west-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
            
        }
    }
}
