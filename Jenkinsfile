pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3.9.6"
    }

    stages {
        stage('Build') {
            steps {
                // Run Maven.
                sh "mvn compile"
            }
        }

        // stage('Test') {
        //     steps {
        //         sh "mvn test"
        //     }
        // }

        stage('Package') {
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true package"
            }
        }

        stage('Deploy') {
            steps {
                sh "java -jar target/spring-petclinic-*.jar"
            }
        }
    }
}
