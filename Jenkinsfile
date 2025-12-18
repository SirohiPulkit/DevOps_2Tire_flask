pipeline{
    agent any
    stages{
        stage('Clone git repo'){
            steps{
                git branch: 'main', url: 'https://github.com/SirohiPulkit/DevOps_2Tire_flask.git'
            }
        }
        stage('Buld docker images'){
            steps{
                sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy with docker compose'){
            steps{
                // existing container if they are running
                sh 'docker compose down || true'
                // start app, rebuilding flask image
                sh 'docker compose up -d --build'
            }
        }
    }
}