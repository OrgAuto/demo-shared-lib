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
          String log = deploy.myData(env.commit)
          println(log)
        }      
      }
    }
  }
  post {

        always {        
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }

    }
}
