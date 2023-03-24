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
        stage(deploy_to_nexus){
          steps{
             sh 'mvn deploy'
            }
        }
    }
}
