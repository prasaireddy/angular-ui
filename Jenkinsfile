pipeline {
    agent {label 'prasai'} 


    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh 'apt install nodejs=18.16.1'
                sh 'npm install'
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
