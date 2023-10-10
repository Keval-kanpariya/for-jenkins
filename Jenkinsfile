def tcp = "1234"

pipeline {
    agent any
    stages {
        stage('Update dev.env') {
            steps {
                script {
                    // Use sed to replace placeholders with actual values in dev.env
                    sh '''
                    echo $tcp
                    sed -i -e "s|\\\$TCP_PORT|$tcp|g" dev.env
                       '''

                }
            }
        }
    }
}
