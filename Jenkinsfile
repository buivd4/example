pipeline {
    agent any
    stages {
        stage("Pull code"){
            steps{
                checkout scmGit(branches: [[name: 'main']],
                    userRemoteConfigs: [[url: 'https://github.com/buivd4/example.git']])
                sh 'ls -l'
            }
        }
        stage("Execute script"){
            steps{
                sh 'echo Hello from GitHub'
                sh 'chmod u+x execute.sh'
                sh './execute.sh'
            }
        }
    }
}
