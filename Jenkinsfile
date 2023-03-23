 pipeline{
    agent any //means the agent should use "any available node"
    tools{
        maven 'mvn'
    }
    stages{
        stage(clone){
            steps{
                git 'https://github.com/iAlexeze/Trial-web-application.git'
            }
        }
    }
}
