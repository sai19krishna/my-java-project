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
        sh "cp dist/junit-4.10_${env.BUILD_NUMBER}.jar /var/www/html/rectangles/all/"
  }
}
   
      }
    }

