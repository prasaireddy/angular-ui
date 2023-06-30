pipeline {
    agent {label 'prasai'} 


    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh 'node --version'
                sh 'npm install -g npm@latest'
                sh 'npm install --save-dev @angular-devkit/build-angular'
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy'
                sh 'npm run deploy'
                sh 'aws s3 sync dist/angular-demo/ s3://s3forjenkinsbuild123'
            }
        }
    }
}
