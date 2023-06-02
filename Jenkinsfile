pipeline {
    agent any
    stages {
        stage (git) {
            steps{
                git branch: 'main', url: 'https://github.com/vamsibyramala/softwaremakers.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId: '10e05f26-2244-4709-aa35-ea802c18aeed', path: '', url: 'http://65.2.177.250:8081/')], contextPath: 'test', war: '**/*.war'
            }
        }
    }
}
