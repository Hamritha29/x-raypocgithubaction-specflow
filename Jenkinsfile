pipeline {
    agent any
    
    environment {
        APP_NAME = "SIMPLE_APP"
    }
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Debug environment variables
                    echo "### DEBUG: Environment Variables"
                    echo "ghprbPullId: ${env.ghprbPullId}"
                    echo "ghprbSourceBranch: ${env.ghprbSourceBranch}"
                    echo "ghprbTargetBranch: ${env.ghprbTargetBranch}"
                    echo "CHANGE_BRANCH: ${env.CHANGE_BRANCH}"
                    echo "CHANGE_TARGET: ${env.CHANGE_TARGET}"
                    echo "BRANCH_NAME: ${env.BRANCH_NAME}" 
                    
                    // Determine the source branch
                    // def sourceBranch = env.ghprbSourceBranch ?: env.CHANGE_BRANCH ?: env.BRANCH_NAME ?: 'main'
                    echo "### CHECKOUT from ${ghprbSourceBranch}"
                }
            }
        }
        stage('Stage 1') {
            steps {
                sh """
                    echo "Running Stage 1" 
                    echo "Application Name: \${APP_NAME}"
                """
            }
        }
        
        stage('Stage 2') {
            steps {
                sh 'env | sort'
            }
        }
        
        stage('Stage 3') {
            steps {
                sh '''
                    echo "Current directory:"
                    pwd
                    echo "Listing files:"
                    ls -la
                '''
            }
        }
    }
}
