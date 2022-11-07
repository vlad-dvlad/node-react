pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }

        stage("Test") {
            steps {
                sh "npm test"
            }
        }
        stage('Deliver') {
            steps {
                sh "./jenkins/scripts/deliver.sh"
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh "./jenkins/scripts/kill.sh"
            }
        }
     }
     post {
        always {
      sh 'npm stop'
    }
}
}
        