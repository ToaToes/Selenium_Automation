```
pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                git 'https://github.com/your/repo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Quality Analysis') {
            steps {
                sh 'mvn sonar:sonar'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp target/my-app.war user@server:/path/to/deploy'
            }
        }
        stage('Post-Build') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
                mail to: 'team@example.com', subject: 'Build Status', body: 'Check the build logs!'
            }
        }
    }
}
```
