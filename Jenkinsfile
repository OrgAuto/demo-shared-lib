@Library('slibDemo@') 
import org.local.deploy
import org.local.getToken
def myClass = new deploy.Test()
def myClass1 = new getToken.Get()

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
          script {
            println(myClass.myData(env.commit))
            println(myClass.myList(env.commit))
            println(myClass1.token("Prince"))
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
