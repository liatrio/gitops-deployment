
pipeline {
    agent any
    node {
        manifest = readJSON file: 'manifest.json'
    }
    stages {
        stage('Deploy to Dev') {
            when {
                branch 'dev'
            }
            steps {
                echo "Deploying ${manifest[0]} to Dev"
            }
        }
        stage('Deploy to Staging') {
            when {
                branch 'staging' 
            }
            steps {
                echo 'Deploying to Staging'
            }
        }
        stage('Deploy to Production') {
            when {
                branch 'production' 
            }
            steps {
                echo 'Deploying to Production'
            }
        }
        stage('Run Automated Tests') {
            steps {
                echo 'Running automated tests'
            }
        }
    }
}