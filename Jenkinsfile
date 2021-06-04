@Library('slibDemo') _

pipeline {
  agent any
  environment {
            def commit = "${env.GIT_COMMIT}"
            def workspace = "${WORKSPACE}"
        }
  stages {
    stage ("Test Shared Library"){
      steps{
        welcome()
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
  //post {

    //    always {        
      //      cleanWs disableDeferredWipeout: true, deleteDirs: true
        //}

    //}
}
