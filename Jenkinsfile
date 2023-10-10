pipeline {
    agent any

    environment {
        // Define environment variables with actual values
        TCP_PORT = '12345'
        TCP_HOST = 'example.com'
        TZ = 'America/New_York'
    }

    stages {
        stage('Update dev.env') {
            steps {
                script {
                    // Use sed to replace placeholders with actual values in dev.env
                    sh '''
                        sed -i "s|\\\$TCP_PORT|${env.TCP_PORT}|g" dev.env
                        sed -i "s|\\\$TCP_HOST|${env.TCP_HOST}|g" dev.env
                        sed -i "s|\\\$TZ|${env.TZ}|g" dev.env
                    '''
                }
            }
        }
    }
}
