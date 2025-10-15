pipeline {
    agent any

    tools {
    jdk 'JDK21'      // match the actual name shown in Jenkins > Global Tool Configuration
    maven 'Maven'
}


    stages {
        stage('Checkout') {
            steps {
                echo '🔹 Cloning repository...'
                git branch: 'main', url: 'https://github.com/shrutika0910/java-jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo '🔹 Building Java application...'
                sh 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                echo '🔹 Running Java application...'
                sh 'mvn exec:java -Dexec.mainClass="com.example.HelloWorld"'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed.'
        }
    }
}
