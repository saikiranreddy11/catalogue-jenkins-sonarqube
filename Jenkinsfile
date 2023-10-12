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
                sh "sonar-scan"
            }
        }
    }
}