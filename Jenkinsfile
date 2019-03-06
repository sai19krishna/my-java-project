pipeline {
  agent any
    stages{
    stage('Unit Tests') {
      steps {
        sh 'ant -f test.xml -v'
        junit 'reports/result.xml'
      }
    }
    stage ('build') {
      steps{
        sh 'ant -f build.xml -v'
             }
          }
     stage('deploy') {
        steps {
           sh "cp dist/rectangle_${env.MAJOR_VERSION}.${env.BUILD_NUMBER}.jar /var/www/html/all/${env.BRANCH_NAME}/"
         }
      }
        }
  
  post { 
    always  {
        archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
    }
  }
}
