pipeline {
  agent any
  environment {
    target_cluster = '10.65.182.142'
  }
  stages {
    stage('finish') {
      agent any
      steps {
//        build (job: 'finish_job', propagate: false)
        sh '''set +e

ssh root@$target_cluster -t "pytest -s /var/Nightswatch/jenkins_pipeline_tests/start.py" '''
      }
    }

    stage('print_target_cluster') {
      agent any
      steps {
        sh '''echo $target_cluster'''

      }
    }

  }
}
