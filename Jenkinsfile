pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/HariharanAI/Youtube-Clone-01.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "No build steps required for a static site. Skipping..."
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Define your deployment method
                    echo "Deploying the static files..."
                    
                    // Example: Copy files to an Nginx server
                    sh '''
                    rsync -avz --delete ./ /var/www/html/youtube-clone/
                    '''

                    echo "Deployment complete."
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
