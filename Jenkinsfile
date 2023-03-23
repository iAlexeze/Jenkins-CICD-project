pipeline{
    agent any
    tool{
        maven 'mvn'
    }
    stages{
        stage(vcs-clone){
            steps{
                git 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
        stage(code-build){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}
