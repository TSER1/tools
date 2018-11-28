pipeline {
  agent any
  stages {
    stage('Begin') {
      steps {
        echo 'Start'
      }
    }
    stage('SCM Checkout') {
      steps {
        git(url: 'https://github.com/TimeSyncTechnology/feature.git', branch: 'feature')
      }
    }
    stage('Scripts') {
      parallel {
        stage('Windows') {
          steps {
            bat 'bat wintest.bat'
          }
        }
        stage('Linux') {
          steps {
            sh 'sh linuxtest.sh'
          }
        }
      }
    }
    stage('End') {
      steps {
        echo 'Finish'
      }
    }
  }
}