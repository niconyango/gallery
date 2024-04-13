pipeline{
    agent any
    // tools{
    //     node 'nodejs'
    // }
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
        stage(""){

        }
    }
}
