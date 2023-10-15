pipeline{
    agent{
        node{
            label "AGENT"
        }
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
            sh 'zip -r "C:\\Users\\saiki\\OneDrive\\Desktop\\devops\\repos\\catalogue\\*" '
            }  
        }
        stage("deploy"){
            steps{
                sh 'echo "deploying the catalogue"'
            }
        }
    }
    post{
        always{
            deleteDir()
        }
    }
}