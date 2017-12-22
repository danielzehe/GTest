pipeline {
  agent {
    docker {
      image 'xenon.tum-create.edu.sg:5000/citymos/citymos:november2017'
    }
    
  }
  stages {
    stage('Test') {
      steps {
        sh '''mkdir -p build
cd build 
cmake ..
make '''
      }
    }
  }
}