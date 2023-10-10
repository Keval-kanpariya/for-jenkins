def myVariable = "1234"

pipeline {
    agent any
    stages {
        stage('Update dev.env') {
            steps {
                script {
                    // Use sed to replace placeholders with actual values in dev.env
                    sh '''
                        sed -i "s|\\\$TCP_PORT|${myVariable}|g" dev.env


                    '''
                }
            }
        }
    }
}
