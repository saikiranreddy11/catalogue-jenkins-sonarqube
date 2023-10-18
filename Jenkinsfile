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
        stage ("extracting the version"){
            steps{
                script {
                    def packageJson = readJSON file: 'package.json'
                    def version = packageJson.version
                    echo "The version from package.json is: ${version}"
                }
            }

        }
        stage("sonarscan"){
            steps{
                sh "sonar-scanner"
            }
        }
        stage("zipping the files"){
            steps{
            sh 'echo "zipping the files"'
            sh 'zip -r catalogue.zip ./*  --exclude=.git --exclude=catalogue.zip '
            }  
        }
    //     stage("uploading the artifact"){
    //         steps{
    //             nexusArtifactUploader(
    //                 nexusVersion: 'nexus3',
    //                 protocol: 'http',
    //                 nexusUrl: '10.40.30.177:8081/',
    //                 groupId: 'com.saikiransudhireddy',
    //                 version: '1.0.1',
    //                 repository: 'catalogue',
    //                 credentialsId: 'nexus-auth',
    //                 artifacts: [
    //                     [artifactId: 'catalogue',
    //                         classifier: '',
    //                         file: 'catalogue.zip',
    //                         type: 'zip']
    //     ]
    //  )
    //         }
    //     }
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