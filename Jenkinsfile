pipeline{
    agent any
    tool{
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
    }
}
