pipeline {
    agent any

    tools {
        jdk 'OpenJDK-11'      // remplacer par le nom configuré dans Jenkins
        maven 'Maven-3.8.8'   // remplacer par le nom configuré dans Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/hwafa/timesheetproject.git'
            }
        }

        stage('Compile') {
            steps {
                sh 'mvn -B clean compile'
            }
        }

        stage('Test (optional)') {
            steps {
                sh 'mvn -B test'
            }
        }
    }

    post {
        success { echo "Build SUCCESS" }
        failure { echo "Build FAILURE" }
    }
}
