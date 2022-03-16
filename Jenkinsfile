pipeline {
    agent any
    tools { 
        maven 'Maven' 
        }
    stages {
        
        stage("Build Maven") {
            steps {
                echo "M2_HOME = ${M2_HOME}"
                sh 'mvn -B clean package'
            }
        }
        stage("Run Gatling") {
            steps {
                sh 'mvn gatling:test'
            }
            post {
                always {
                    gatlingArchive()
                }
            }
        }
    }
}
