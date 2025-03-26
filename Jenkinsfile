pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }        
        
        stage('Deploy to Tomcat server') {
            steps {
            deploy adapters: [tomcat9(credentialsId: 'tompass', path: '', url: 'http://18.188.55.51:8080/')], contextPath: 'myapp', war: '**/*.war'            }
            }
        }
    }
}
