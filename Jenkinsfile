pipeline {
  agent none
  stages {    
    stage('init'){
      parallel{
      stage('init1'){
      agent {
        label 'slave1'
      }
      steps{
        sh ' python3 --version'
        
      }
    }
        stage('init2'){
      agent {
        label 'slave2'
      }
      steps{
        sh ' python3 --version '
        
      }
    }
      
    }
    }
    
    stage('build1') {
      agent {
        label 'slave1'
      }
      
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
      
    
    stage('build2') {
      agent {
        label 'slave2'
      }
      
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test2') {
      agent {
        label 'slave2'
      }
    
      steps {
        sh 'python3 test.py'
      }   
    }
  }
}
