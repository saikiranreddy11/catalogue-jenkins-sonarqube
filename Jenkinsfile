pipeline{
    agent{
        node{
            label "AGENT"
        }
    }
    options {
        ansiColor('xterm')
    }
    stages{
        stage("Installing dependecies"){
            steps{
            sh 'npm install'
            }
        }
        // stage("sonarscan"){
        //     steps{
        //         sh "sonar-scanner"
        //     }
        //}
        stage("zipping the files"){
            steps{
            sh 'echo "zipping the files"'
            sh 'zip -r catalogue.zip ./*  --exclude=.git --exclude=catalogue.zip '
            }  
        }
        stage("deploy"){
            steps{
                sh 'echo "deploying the catalogue"'
            }
        }
    }
    // post{
    //     always{
    //         deleteDir()
    //     }
    // }
}