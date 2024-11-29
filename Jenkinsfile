pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        packageversion = ''
    }
  
    options{
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
        // ansiColor('xterm')
    }
   
    stages {
        stage('Get the version') {
            steps {
                script {
                    def packagejson = readJson  file: 'package.json'
                    packageversion = packagejson.version
                    echo " application version: $packageversion"
                }
            }
        } 
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            
            steps {
                sh """
                    echo "Here I write shell script"
                """
            }
        }
        
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success { 
            echo 'I will  say Hello when pipeline is success'
        }
    }
}