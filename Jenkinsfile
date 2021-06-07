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
          def repo_dir = deploy.GetCRepoDir()
          def delta_file_list = deploy.GetDeltaFiles(commit)
          def deploy_list = deploy.GetDeployScripts(delta_file_list)
          for (script in deploy_list) {
            def extension = deploy.GetExtension(script)
            def script_basename = deploy.GetBaseName(script, extension)
            println(script)
            println(deploy.GetScriptContent(script, repo_dir))
          }
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
