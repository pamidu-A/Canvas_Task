pipeline {
  agent {label 'generic'}
  options {
    disableConcurrentBuilds()
  }
  stages{
    //Run Commands insidecker image
    stage('Pull Docker Image') {
      steps {
        script {
          docker.withRegistry('https://002712100444.dkr.ecr.us-east-2.amazonaws.com/', 'ecr:us-east-2:aws-rr-automation') {
            docker.image('002712100444.dkr.ecr.us-east-2.amazonaws.com/jenkins/kubernates:v5').pull()         
          }
        }
      }
    }
    stage('Run inside Docker Image') {
      //agent {
       // docker { image '0271210044.dkr.ecr.us-east-2.amazonaws.com/jekins/kubernates:v1' }
      //}
      steps {
        //sh 'docker system prne -af'
        sh 'docker run 002712100444.dkr.ecr.us-east-2.amazonaws.com/jenkins/kubernates:v5'
       
      }
    }
  }  
}
