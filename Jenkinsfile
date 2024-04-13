pipeline{
    agent any
    stages{
        stage("Clone Code"){
            steps{
            git branch: "master",url: 'https://github.com/niconyango/gallery.git'
            }
        }
        stage("Build Code"){
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
            }
        }
    }
}
