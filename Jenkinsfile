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
  }
}
