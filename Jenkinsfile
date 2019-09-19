pipeline {
  
  agent any
  
  stages {
    
    stage('test') {
      
      agent { docker { image 'python' } }
      
      steps { 
        sh 'python --version' 
      }
    }
    
  }

}
