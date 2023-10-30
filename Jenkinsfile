pipeline {
  agent any
  stages {
    stage('Python version') {
      steps {
        sh 'python3 --version'
      }
    }
    stage('Sonar') {
      steps {
        script {
          withSonarQubeEnv('SonarScan_Test') {
            sh "${scannerHome}/bin/sonar-scanner"
          }
        }
      }
    }
    stage('Build') {
      steps {
        sh 'python3 CAT_WeeB/_Test1.py'
        // sh 'python -m py_compile CAT_WeeB/_Test1.py -x /home/sds/YBL_WS/build_Test1.pyc'
      }
    }
  }
}