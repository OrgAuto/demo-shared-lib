@Library('slibDemo') _

pipeline {
  agent any
  environment {
            commit = "${env.GIT_COMMIT}"
        }
  stages {
    stage ("Test Shared Library"){
      steps{
        welcome("Priyabrata Mohanty")
      }
    }
    stage ("Test Shared Lib Function"){
      steps {
        script {
          println("Current commit id is: \n" + env.commit)
          println(deploy.myData(env.commit))
        }      
      }
    }
  }
}
