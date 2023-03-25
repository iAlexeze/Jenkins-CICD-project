pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage('code clone'){
           steps{
            git 'https://github.com/iAlexeze/Trial-web-application.git' 
            }
        }
      stage('code build'){
        steps{
            sh 'mvn clean package'
            }
        }
      stage('code quality analysis'){
        steps{
            sh 'sonar:sonar'
            }
        }
      stage('artifact backup'){
        steps{
            sh 'mvn deploy'
            }
        }
      stage('prod deployment'){
          steps{
        deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://34.204.101.17:8080/')], contextPath: '/iAlexapp', war: 'target/*.war'
        }
        }
    }
}
