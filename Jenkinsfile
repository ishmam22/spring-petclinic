pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat './mvnw package'
      }
    }

    stage('Test') {
      steps {
        bat 'mvn test'
      }
    }

    stage('Package') {
      steps {
        bat 'mvn package'
      }
    }

    stage('Deploy') {
      steps {
        bat 'mvn deploy'
      }
    }

    stage('Email') {
      steps {
        emailext(subject: 'Build Passed', body: 'Passed', from: 'jenkins', to: 'ishmammurtaza@gmail.com')
      }
    }
    
  }
  post {
    success {
        mail to: 'ishmammurtaza@gmail.com',
             subject: "Passed Pipeline",
             body: "Passed Build"
    }
}
}
