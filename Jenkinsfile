@Library('slibDemo') _
import com.org.deploy

pipeline {
  agent any
  environment {
            // Get the commit log
            COMMIT_LOG = "${com.org.deploy.myData}"
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
          def commit = env.GIT_COMMIT
          println(env.COMMIT_LOG(commit))
        }      
      }
    }
  }
}
