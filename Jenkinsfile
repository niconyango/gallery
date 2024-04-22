pipeline{
    environment{
        BUILD_NUM=''
    }
    agent any
    tools{
        nodejs 'node'
    }
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
                slackSend color: 'good', message: "Build N°: ${env.BUILD_NUMBER} was successfully deployed in 'https://gallery-oold.onrender.com/'"
            }
        }
    }
    post {
        success {
            emailext attachLog: true, 
                body:
                    """
                    <p>EXECUTED: Job <b>\'${env.JOB_NAME}:${env.BUILD_NUMBER})\'</b></p>
                    <p>
                    View console output at 
                    "<a href="${env.BUILD_URL}">${env.JOB_NAME}:${env.BUILD_NUMBER}</a>"
                    </p> 
                    <p><i>(Build log is attached.)</i></p>
                    """,
                subject: "Status: 'SUCCESS' -Job \'${env.JOB_NAME}:${env.BUILD_NUMBER}\'", 
                to: 'bluckcomet@gmail.com'
        }
        failure {
            emailext attachLog: true, 
                body:
                    """
                    <p>EXECUTED: Job <b>\'${env.JOB_NAME}:${env.BUILD_NUMBER})\'</b></p>
                    <p>
                    View console output at 
                    "<a href="${env.BUILD_URL}">${env.JOB_NAME}:${env.BUILD_NUMBER}</a>"
                    </p> 
                    <p><i>(Build log is attached.)</i></p>
                    """,
                subject: "Status: FAILURE -Job \'${env.JOB_NAME}:${env.BUILD_NUMBER}\'", 
                to: 'bluckcomet@gmail.com'
        }
    }
}
