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
          slackSend channel: '#random', color: 'green', message: 'SUCCESS'
       }

       failure {
          slackSend channel: '#random', color: 'red', message: 'FAILURE'
       }
   }


}