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
                sh 'npm test'
            }
        }
        stage("Deploy Code"){
            steps{
                //sh 'npm run'
                echo 'Deploying the code' 
                slackSend color: 'good',message:'Deployment Successful'
            }
        }
    }
}
