// 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

pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage(clone){
            steps{
                git credentialsId: 'Ace-cred', url: 'git@github.com:iAlexeze/Trial-web-application.git'
            }
          
        }
        stage(build){
             steps{
                 sh 'mvn clean package'
            }
            
        }
        stage(analysis){
            steps{
                 sh 'mvn sonar:sonar'
            }
            
        }
        stage(backup){
            steps{
                  sh 'mvn deploy'
            }
           
        }
        stage(deploy){
              steps{
            deploy adapters: [tomcat8(credentialsId: 'tomcred', path: '', url: 'http://34.224.94.40:8080/')], contextPath: null, war: 'target/*war'
           // deploy adapters: [tomcat8(credentialsId: 'tomcred', path: '', url: 'http://54.197.33.185:8080')], contextPath: '/target/*war', war: ''
  
            }
        }
    }
}

