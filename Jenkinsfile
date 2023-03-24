pipeline{
    agent any
    tools{
        maven 'mvn'
    }
    stages{
        stage(vcs_clone){
            steps{
                git 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
        stage(code_build){
            steps{
                sh 'mvn clean package'
            }
        }
        stage(quality_analysis){
            steps{
                sh 'mvn sonar:sonar'
            }
        }
        stage(backup_with_nexus){
          steps{
             sh 'mvn deploy'
            }
        }
        stage(deploy_to_tomcat){
            steps{
             deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: '')], contextPath: '/iAlexapp', war: '/target/*war'
            }
        }
    }
}
