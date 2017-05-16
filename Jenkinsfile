pipeline {
  agent any
  stages {
    stage('Saludo') {
      steps {
        parallel(
          "Saludo": {
            echo 'Hello World DevOps!'
            
          },
          "Obtener cambios SCM": {
            git 'https://github.com/juanrestrepoc/sampleapp.git'
            
          }
        )
      }
    }
    stage('Pruebas unitarias') {
      steps {
        bat 'mvn clean test'
        junit 'target/surefire-reports/*.xml'
      }
    }
  }
}