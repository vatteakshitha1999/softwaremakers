pipeline {
    agent any
    stages {
        stage (SCM) {
            steps {
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
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.232.127.170:8080/')], contextPath: 'vamsi', war: '**/*.war'
            }
        }
    }
}
