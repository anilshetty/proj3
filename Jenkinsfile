pipeline {
  
  agent { docker { image 'python' } }
  
  stages {
    
    stage('test') {
      
      agent any
      steps { 
        sh 'python --version' 
      }
    }
    
  }

}
