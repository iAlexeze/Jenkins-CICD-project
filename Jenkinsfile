pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage('Git Clone'){
            steps{
                git 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
        stage('Code Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Quality Analysis'){
            steps{
                sh 'mvn sonar:sonar'
            }
        }
        stage('Backup with Nexus'){
          steps{
             sh 'mvn deploy'
            }
        }
        stage('Deploy to Tomcat'){
            steps{
             deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://34.204.101.17:8080/')], contextPath: '/iAlexapp', war: 'target/*war'
            }
        }
    }
}
