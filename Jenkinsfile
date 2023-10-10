def tcp = "1234"

pipeline {
    agent any
    stages {
        stage('Update dev.env') {
            steps {
                script {
                    echo "tcp = ${tcp}" // Print the value of tcp for debugging

                    // Use sed to replace placeholders with actual values in dev.env
                    sh """
                        sed -i -e "s|\\\$TCP_PORT|${tcp}|g" dev.env
                    """
                }
            }
        }
    }
}
