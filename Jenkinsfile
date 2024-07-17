pipeline{
    agent none
//     agent {
//     node {
//         label 'WORKSTATION'
//     }
// }

    environment {
         SAMPLE_URL = "google.com"
         SLACK_TOKEN = credentials('slack')
    }

    stages{
        stage('One'){
            agent {
               node {
                  label 'NODEJS'
                }
            }
            steps{
                sh 'echo Hello World'
                sh 'echo ${SAMPLE_URL}'
                sh 'echo ${SLACK_TOKEN}'
            }
        }
        stage('Two'){
            agent {
               node {
                  label 'JAVA'
              }
            }
            steps{
                sh 'echo Hello World'
            }
        }
    }


   post {
       success {
          slackSend color: 'good', message: 'SUCCESS'
       }

       failure {
          slackSend color: 'danger', message: 'FAILURE'
       }
   }


}