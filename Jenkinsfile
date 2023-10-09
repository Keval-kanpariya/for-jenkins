pipeline {
    agent any

    stages {
        stage('Environment Variable') {
            steps {
                script {
                    def devEnvFile = readFile('dev.env')
                    def envVars = [:]
                    devEnvFile.eachLine { line ->
                        def (key, value) = line.split('=')
                        envVars[key.trim()] = value.trim()
                    }
                    // Set the environment variables
                    withEnv(envVars) {
                        echo "Environment variables loaded from dev.env:"
                        envVars.each { key, value ->
                            echo "${key}=${value}"
                        }
                    }
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
