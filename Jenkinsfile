pipeline {
    agent any
    stages {
        stage (git) {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
            deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://35.154.193.213/8081/')], contextPath: 'karna', war: '**/*.war'
            }
        }
    }
}
