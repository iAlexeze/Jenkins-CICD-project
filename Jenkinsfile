pipeline{
    agent any
    tool{
        maven 'mvn'
    }
    stages{
        stage(vcs-clone){
            steps{
                git clone 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
    }
}
