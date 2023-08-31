pipeline {
    agent any
    
    environment {
        RENDER_EMAIL = credentials('render_email')
        RENDER_PASSWORD = credentials('render_password')
    }
    
    stages {
        // ... other stages ...

        stage('Deploy') {
            steps {
                // Install Render CLI (if not already installed)
                sh 'curl -o /usr/local/bin/render https://render.com/cli/latest/linux/render'
                sh 'chmod +x /usr/local/bin/render'

                // Log in to Render using environment variables
                sh "render login $RENDER_EMAIL $RENDER_PASSWORD"

                // Deploy to your service
                sh 'render up -s myportfolio-ix7q'
            }
        }
    }
}