pipeline {
 agent {
   docker {
                    image 'python:2-alpine' 
                }
            }
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python3 test.py'
      }   
    }
  }
}
