@Library('slibDemo') import com.org.deploy
def slibDemo = new deploy(this)

pipeline {
  agent any
  environment {
            // Get the commit log
            commit = "${env.GIT_COMMIT}"
        }
  stages {
    stage ("Test Shared Library"){
      steps{
        welcome("Priyabrata Mohanty")
      }
    }
    stage ("Test Shared Lib Class"){
      steps {
        script {
          println("Current commit id is: \n" + env.commit)
          deploy.myData(env.commit)
        }      
      }
    }
  }
}
