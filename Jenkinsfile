pipeline {
    agent any
 environment {
        TCP_PORT = readFile('dev.env').trim().split('=')[1].trim()
        TCP_HOST = readFile('dev.env').trim().split('=')[3].trim()
        TZ = readFile('dev.env').trim().split('=')[5].trim()
    }
    stages {
        stage('Print Environment Variables') {
            steps {
                script {
                    echo "TCP_PORT: ${env.TCP_PORT}"
                    echo "TCP_HOST: ${env.TCP_HOST}"
                    echo "TZ: ${env.TZ}"
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Hello from build stage'
                echo 'Hello from build stage 2'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Hello from deploy stage'
            }
        }

        stage('Test') {
            steps {
                echo 'Hello from test stage'
            }
        }

        stage('Release') {
            steps {
                echo 'Hello from release stage'
            }
        }
    }
}
