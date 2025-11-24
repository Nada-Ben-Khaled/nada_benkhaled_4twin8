pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                git branch: 'main', url: 'https://github.com/Nada-Ben-Khaled/nada_benkhaled_4twin8.git'
            }
        }

        stage('Compile Stage') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQubeServer') { // "SonarQubeServer" = Nom configuré dans Jenkins
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline exécuté avec succès !'
        }
        failure {
            echo 'Échec du pipeline !'
        }
    }
}
