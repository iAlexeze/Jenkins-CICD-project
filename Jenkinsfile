pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage('code clone'){
           steps{
            git 'https://github.com/iAlexeze/Jenkins-CICD-project.git' 
            }
        }
      stage('code build'){
        steps{
            sh 'mvn clean package'
            }
        }
      stage('code quality analysis'){
        steps{
            sh 'mvn sonar:sonar'
            }
        }
      stage('artifact backup'){
        steps{
            sh 'mvn deploy'
            }
        }
      stage('prod deployment'){
          steps{
        deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://54.165.81.113:8080/')], contextPath: '/iAlexapp', war: 'target/*.war'
        }
        }
    }
}

