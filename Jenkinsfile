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
        stage("sonarscan"){
            steps{
                sh "sonar-scanner"
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