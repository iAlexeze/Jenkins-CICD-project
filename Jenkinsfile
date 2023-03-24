pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage(vcs clone){
            steps{
                git 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
        stage(code build){
            steps{
                sh 'mvn clean package'
            }
        }
        stage(quality analysis){
            steps{
                sh 'mvn sonar:sonar'
            }
        }
        stage(backup with nexus){
          steps{
             sh 'mvn deploy'
            }
        }
        stage(deploy to tomcat){
            steps{
               deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://34.204.101.17:8080/')], contextPath: 'null', war: 'target/*war'
           }
        }
    }
}
