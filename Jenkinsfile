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
        println("Stage 1")
          // welcome()
      }
    }
    stage ("Test Shared Lib Function"){
      steps {
        script {
          String commit = deploy.GetCommit()
          println(commit)
          def repo_dir = deploy.GetCRepoDir()
          println(repo_dir)
          def file_list = deploy.GetDeltaFiles(commit)
          println("Delta list")
          println(deploy.GetDeltaFiles(commit))
          println("Deployable files list")
          println(deploy.GetDeployScripts(file_list))
          def deploy_list = deploy.GetDeployScripts(file_list)
          for (script in deploy_list) {
            deploy.GetExtension(script)
          }
        }      
      }
    }
  }
  // post {
  //      always {        
  //          cleanWs disableDeferredWipeout: true, deleteDirs: true
  //       }
  //   }
}
