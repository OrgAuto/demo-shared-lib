@Library('slibDemo') _
import com.org.deploy

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
          def commit = env.GIT_COMMIT
          def dp = new com.org.deploy()
          println(dp.myData(commit))
        }      
      }
    }
  }
}
