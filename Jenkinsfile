pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo yarn install"
                sh "sudo yarn run build"
            }
        }

        stage("Test") {
            steps {
                sh "yarn test"
            }
        }
     }
}
        