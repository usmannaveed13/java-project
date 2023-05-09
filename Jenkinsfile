pipeline {
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat10(credentialsId: '4c7ff5d6-53e4-403b-b93c-242eec5533c1', path: '',
                url: 'http://ec2-16-170-15-14.eu-north-1.compute.amazonaws.com:8080/')],
				contextPath: 'javawebappNew', war: '**/*.war'
            }
        }
    }
}
