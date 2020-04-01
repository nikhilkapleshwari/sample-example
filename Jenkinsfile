pipeline {
    agent any

    stages {
        stage('clean') {
            steps {
                echo 'cleaning previous release data.'
                sh "mvn release:clean"
            }
        }
        stage('prepare') {
            steps {
                echo 'preparing for release.'
                sh "mvn --batch-mode release:prepare"
            }
        }
        stage('install & deploy') {
            steps {
                echo 'installing & deploying release'
                sh "mvn release:perform -Darguments="-Dmaven.javadoc.skip=true -Dusername=admin -Dpassword=Password12345" "
            }
        }
    }
}