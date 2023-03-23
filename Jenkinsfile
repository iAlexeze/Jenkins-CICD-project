pipeline{
    agent any
    tools{
        mvn 'mvn'
    }
    stages{
        stage(vcs-clone){
            steps{
                git clone 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
    }
}
