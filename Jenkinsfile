pipeline {
    agent any

    tools {
        // Install the Maven version configured as "maven-3.6.3" and add it to the path.
        maven "maven-3.6.3"
    }

    stages {
        stage('Build') {
            steps {
                // Checkout code from GitHub repository
              //  git credentialsId: 'SefaliSabnam', branch: 'feature1', url: 'https://github.com/SefaliSabnam/my-jenk-app.git'

                // Run Maven build
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
