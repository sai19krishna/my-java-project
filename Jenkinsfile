pipeline {
  agent any
  stages {
        stage('Unit Tests') {
      steps {
        sh 'ant -f test.xml -v'
        junit 'reports/result.xml'
      }
    }
    stage('build') {
      steps {
        sh 'ant -f build.xml -v'
      }
    }
    stage('deploy'){
      steps{
        sh "scp dist/recantgle_${env.BUILD_NUMBER}.jar /var/www/html/rectangles/all/"
  }
}
   
      }
    }

