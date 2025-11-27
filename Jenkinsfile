pipeline {
    agent any

    stages {
        stage('Hello World') {
            steps {
                echo ' Pipeline depuis Jenkinsfile - avec-maven'
            }
        }

        stage('List Files') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Check Java & Maven') {
            steps {
                sh 'java -version || echo "Java non installé"'
                sh 'mvn --version || echo "Maven non installé"'
            }
        }

        stage('Build Maven') {
            steps {
                script {
                    try {
                        sh 'mvn clean compile'
                        echo ' Build réussi!'
                    } catch (Exception e) {
                        echo ' Build échoué - Maven probablement non configuré'
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminé - Jenkinsfile v1.0'
        }
    }
}