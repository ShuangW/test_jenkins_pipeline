pipeline {
  agent any
  stages {
    stage('nba_main_release') {
      steps {
        echo 'build'
      }
    }
    stage('up_rpm_release') {
      parallel {
        stage('up_rpm_release') {
          steps {
            echo 'up_rpm_release'
          }
        }
        stage('nba_deploy') {
          steps {
            echo 'nba_copy_to_pxe'
            echo 'nba_deploy'
          }
        }
      }
    }
    stage('up_rpm_test') {
      parallel {
        stage('up_rpm_test') {
          steps {
            echo 'up_rpm_test'
          }
        }
        stage('nba_test') {
          steps {
            echo 'nba_test'
          }
        }
      }
    }
    stage('aggregate_report') {
      steps {
        echo 'aggregate_report'
      }
    }
  }
}