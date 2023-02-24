pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage(clone){
            steps{
                  git 'https://github.com/iAlexeze/Trial-web-application.git'
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
            deploy adapters: [tomcat8(credentialsId: 'tomcred', path: '', url: 'http://54.197.33.185:8080/')], contextPath: null, war: 'target/*war'
  
            }
        }
    }
}

