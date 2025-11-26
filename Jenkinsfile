pipeline {
  agent any
  stages {
    stage('Checkout') { steps { git branch: 'main', url: 'YOUR_GITHUB_REPO_URL' } }
    stage('Install Dependencies') { steps { sh 'npm install' } }
    stage('Run Tests') { steps { sh 'npm test' } }
    stage('Deploy to Server') { 
      steps { 
        sh 'ssh ubuntu@YOUR_SERVER_IP "cd /var/www/app && git pull && npm install && pm2 restart all"' 
      } 
    }
  }
}
