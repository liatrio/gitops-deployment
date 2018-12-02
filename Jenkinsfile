def manifest
pipeline {
    agent any
    stages {
        stage('Deploy to Dev') {
            when {
                branch 'dev'
            }
            steps {
                script {
                    manifest = readJSON file: 'manifest.json'
                    echo "Deploying ${manifest.manifest_version} to Dev environment ${manifest.environments.dev.host}"
                }
            }
        }
        stage('Deploy to Staging') {
            when {
                branch 'staging' 
            }
            steps {
                script {
                    manifest = readJSON file: 'manifest.json'
                    echo "Deploying ${manifest.manifest_version} to Staging environment ${manifest.environments.staging.host}"
                }
            }
        }
        stage('Deploy to Production') {
            when {
                branch 'production' 
            }
            steps {
                script {
                    manifest = readJSON file: 'manifest.json'
                    echo "Deploying ${manifest.manifest_version} to Production environment ${manifest.environments.production.host}"
                }
            }
        }
        stage('Run Automated Tests') {
            steps {
                echo 'Running automated tests'
            }
        }
    }
}