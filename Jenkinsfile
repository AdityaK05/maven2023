pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AdityAK05/maven2023.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Verify WAR') {
            steps {
                sh 'ls -l target/'
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook playbook.yml -i hosts.ini'
            }
        }
    }
}
