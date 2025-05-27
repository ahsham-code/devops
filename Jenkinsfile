pipeline { 
    agent any 
 
    tools { 
        maven 'Maven' // Use the Maven tool configured in Jenkins 
    } 
 
    stages { 
        stage('Checkout') { 
            steps {  
                git branch: 'main', url: 'https://github.com/ahsham-code/devops.git'
            } 
        } 
 
        stage('Build') { 
            steps { 
                bat 'mvn clean package' 
            } 
        } 
 
        stage('Test') { 
            steps { 
                bat  'mvn test' 
            } 
        } 
 
        stage('Deploy') { 
            steps { 
                echo 'Deploying application...' 
            } 
        } 
    } 
 
    post { 
        success { 
            echo 'Build and Test Passed!' 
        } 
        failure { 
            echo 'Build Failed!' 
        } 
    } 
} 
