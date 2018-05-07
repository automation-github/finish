pipeline {
  agent any
  environment {
    target_cluster = '10.65.182.142'
  }
  stages {
    stage('finish') {
      try {
        agent any
        steps {
  //        build (job: 'finish_job', propagate: false)
  //        build job: 'finish_job'
        sh '''set +e

  ssh root@$target_cluster -t "pytest -s /var/Nightswatch/jenkins_pipeline_tests/finish.py" '''
        currentBuild.result = 'SUCCESS'
        }
      }
    } catch(e) {
      currentBuild.result = "FAILURE"
    }

    stage('print_target_cluster') {
      agent any
      steps {
        sh '''echo $target_cluster'''

      }
    }

  }
}
