pipeline {
  agent any

  tools {
    maven 'maven'
  }

  stages {
    stage('Echo Version') {
      steps {
        echo 'Maven Version'
        sh 'mvn --version'
      }
    }

    stage('Build JAR') {
      steps {
        echo 'Building project...'
        sh 'mvn clean package -DskipTests=true'
      }
    }

    stage('Run Unit Tests') {
      steps {
        echo 'Running Unit Tests...'
        sh 'mvn test'
      }
    }
  }

  post {
    success {
      echo '✅ Build and tests completed successfully.'
    }
    failure {
      echo '❌ Build or tests failed.'
    }
  }
}
