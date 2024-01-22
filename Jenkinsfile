pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3.9.6"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/theo77186/SpringPetClinic.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                // Run Maven.
                sh "mvn compile"
            }
        }

        stage('test') {
            steps {
                sh "mvn test"
            }
        }
    }
}
