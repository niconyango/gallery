pipeline{
    environment{
        BUILD_NUM=''
    }
    agent any
    // tools{
    //     nodejs 'node'
    // }
    stages{
        stage("Clone Code"){
            steps{
            git branch: "master",url: 'https://github.com/niconyango/gallery.git'
            }
        }
        stage("Installing Dependencies"){
            steps{
                sh 'npm install'
            }
        }
        stage("Test Code"){
            steps{
                sh 'npm test'
            }
        }
        stage("Deploy Code"){
            steps{
                sh 'npm run'
                // echo 'Deploying the code' 
                
            }
        }
        stage("User Notification"){
            steps{
                //slackSend color: 'good',message:'Deployment Successful'
                slackSend color: 'good', message: "The deployment is successful for Build N°: ${env.BUILD_NUMBER}"
            }
        }
        // stage{
        //     steps{
        //         post{
        //             always{
        //                 emailext(
        //                     subject: 'Deplyment Status.{currentBuild.result}',
        //                     body: '''<html>
        //                     <body>
        //                     </body>
        //                     <html>
        //                     ''',
        //                 )
        //             }

        //         }
        //     }

        // }
    }
}
