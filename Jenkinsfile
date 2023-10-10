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
                        // git remote add origin https://github_pat11A6IUE3Q0joKgfJEXUJ0w_osSFeU1B8yh9g4wXU6GMG65UlQBn8j9H4PNLtwI1ThWCGXW7SEP41J1bpSb@github.com/Keval-kanpariya/for-jenkins.git
                        git add .
                        git commit -m "Updated dev.env and Jenkins pipeline script"
                        git push origin main
                    """
                }
            }
        }
    }
}
