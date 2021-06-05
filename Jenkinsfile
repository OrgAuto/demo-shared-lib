@Library('slibDemo') _
import org.local.deploy
import org.local.getToken


pipeline {
  agent any
  environment {
            def commit = "${env.GIT_COMMIT}"
            def workspace = "${WORKSPACE}"
        }
  stages {
    stage ("Test Shared Library"){
      steps{
          // welcome()
          script {
            def myClass = new deploy()
            def myClass1 = new getToken()
            myClass.myData(env.commit)
            myClass.myList(env.commit)
            myClass1.token("Prince")
          }

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
