pipeline {
    agent any
    environment {
        GIT_URL = "git@github.com:Atul-Bhandari-IOPShub/mvnS3.git"
        BRANCH_NAME = "$Branch"
    } 	
    stages {
        stage("code checkout") {
            steps {
                git url: "$GIT_URL", branch: "$BRANCH_NAME"
                
            }
        }
        stage('Build and install') {
            steps {
                dir("my-app") {
                    sh 'mvn install'
                }
            }
        }
        stage('Deploy') {
            steps {
                dir("my-app"){
                sh 'mvn deploy'
                }
            }
        }
    }
}
