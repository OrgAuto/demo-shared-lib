@Library('slibDemo') _
import com.org.deploy

pipeline {
  agent any
  environment {
            // Get the commit log
            commit = "${env.GIT_COMMIT}"
            COMMIT_LOG = "${com.org.deploy.myData(commit)}"
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
          println("Current commit log is: \n" + env.COMMIT_LOG)
        }      
      }
    }
  }
}
