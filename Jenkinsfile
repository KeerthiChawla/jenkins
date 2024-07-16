pipeline{
    agent none
//     agent {
//     node {
//         label 'WORKSTATION'
//     }
// }
    stages{
        stage('One'){
            agent {
               node {
                  label 'NODEJS'
                }
            }
            steps{
                sh 'echo Hello World'
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
          slackSend channel: '#random', color: 'danger', message: 'FAILURE'
       }
   }


}