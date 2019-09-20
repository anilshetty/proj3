pipeline {

  agent none

  stages {

    stage('build'){
      agent { docker { image 'python'} }
      when { branch 'master' }
      steps {
        sh 'python --version'
      }
    }
    stage('test'){
      agent { docker { image 'nginx' } }
      when { branch 'feature' }
      steps {

        sh 'nginx -v'
      }
    }
    stage('deploy'){
      agent { docker { image 'httpd' }}
      steps {

        sh 'httpd -v'
      }
    }

  }
  post {

     always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }

  }
}
