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

                    // Configure the Git remote URL with SSH
                    sh """
                        git config --global user.email "your-email@example.com"
                        git config --global user.name "keval-kanpariya"
                        git remote set-url origin git@github.com:Keval-kanpariya/for-jenkins.git
                        git add .
                        git commit -m "Updated dev.env and Jenkins pipeline script"
                        git push origin main
                    """
                }
            }
        }
    }
}
