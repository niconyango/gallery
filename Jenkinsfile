pipeline{
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
                //sh 'npm test'
                sh 'node test'
            }
        }
        stage("Deploy Code"){
            steps{
                //sh 'npm run'
                echo 'Deploying the code' 
            }
        }
        stage("Send Message"){
            steps{
                slackSend color: 'good',message:'Deployment Successful'
            }
        }
    }
}
