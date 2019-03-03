pipeline {
  agent any
  stages{
    stage ('build') {
      steps{
        sh 'ant -f build.xml --v'
             }
          }
        }
  
  post { 
    always  {
        archiveArtifacts artifacts: 'junit-4.10.jar',fingerprint: true
    }
  }
}
