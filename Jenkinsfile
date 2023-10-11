def tcp = "fdxg"

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
                        git init
                        git config --global user.email "your-email@example.com"
                        git config --global user.name "keval"
                        #git stash save "Stash changes in dev.env"
                        sed -i -e "s|\\\$TCP_PORT|${tcp}|g" dev.env
                        
                         """
                
                   
                }
            }
        }
         stage('anaother stage') {
                    steps {
                        script {
                    sh """
                        
                        git remote set-url origin https://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@github.com/Keval-kanpariya/for-jenkins.git
                        git add .
                        git commit -m "Updated dev.env and Jenkins pipeline script"
                        #git checkout main
                        git push origin main
                    """
                        }
                        }
                    }
    }
}
