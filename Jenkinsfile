pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "yarn install"
                sh "yarn run build"
            }
        }

        stage("Test") {
            steps {
                sh "yarn test"
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
}
        