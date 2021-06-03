@Library('slibDemo') _
pipeline {
  agent any
  stages {
    stage ("Test Shared Library"){
      steps{
        welcome("Priyabrata Mohanty")
      }
    }
    stage ("Test Shared Lib Class"){
      steps {
        script {
          def commit = ${env.GIT_COMMIT}
          deploy.deploy.myData("${commit}")
        }      
      }
    }
  }
}
