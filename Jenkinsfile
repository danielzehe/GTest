pipeline {
  agent {
    docker {
      image 'xenon.tum-create.edu.sg:5000/citymos/citymos:november2017'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh '''mkdir -p build
cd build 
cmake ..
make '''
      }
    }
    stage('Test') {
      steps {
        sh 'build/runTests --gtest_output=xml:gtestresults.xml'
      }
      post {
        always {
          xunit 'build/gtestresults.xml'
          
        }
        
      }
    }
  }
}