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
            sh 'echo "zipping the files"'
            zip -r "C:/Users/saiki/OneDrive/Desktop/devops/repos/catalogue/*" catalogue.zip  
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