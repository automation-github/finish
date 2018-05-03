pipeline {
  agent any
  environment {
    target_cluster = '10.65.182.142'
  }
  stages {
    stage('finish') {
      agent any
      steps {
        build (job: 'finish', propagate: false)
      }
    }



  }
}
