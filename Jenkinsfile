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
        stage("Build"){
            steps{
                sh '/opt/homebrew/bin/mvn package'
            }
        }
        stage("Test"){
            steps{
                sh '/opt/homebrew/bin/mvn verify'
            }
        }
        stage("Store Artifactory"){
            steps{
                sh 'ls -l target/'
            }
        }
    }
}
