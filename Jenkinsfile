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
    stage('Pruebas Unitarias') {
      steps {
        sh 'mvn clean test'
      }
    }
  }
}