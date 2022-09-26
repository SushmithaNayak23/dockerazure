// multistage
pipeline {
    agent any

        stages {
            stage('Source') {
                steps {
                    git url: 'https://github.com/Anandasb149/SpringMysqlDemo.git'
                }
            }
            stage('Build') {
                steps {
                    script {
                        def mvnHome = tool 'Maven_Home'
                        bat "${mvnHome}\\bin\\mvn -B verify"
                    }
                }
            }
             stage('Build docker image') {
                steps {
                    script {
                        bat 'docker-compose up'
                    }
                }
            }              
        }
}
