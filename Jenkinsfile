pipeline {
    agent any{
        node {
            label 'my_pc'
            }
    }
    
    stages {

         stage('Checkout') {
            steps {
                echo 'OK'
                git branch: 'main', url: 'https://github.com/fiyona2002/mavgit.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'This is building stage'
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                echo 'This is testing stage'
                sh 'mvn test'
            }
        }
        
        stage('Integration Test') {
            steps {
                // Assuming you have Selenium tests in your project
                echo 'This is integration stage'
                sh 'mvn verify'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'This is deployment stage' 
                // Add deployment steps if applicable
            }
        }
    }
    
    post {
        always {
            // Clean up workspace
            deleteDir()
        }
        
    }
}
