pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'  // Set this to the path of your JDK
        PATH = "${env.JAVA_HOME}\\bin;${env.PATH}"
    }
    stages {
        stage('Build') {
            steps {
				bat 'mvn -B -U -e -V clean -DskipTests package'
            }
        }

        stage('Test') {
            steps {
				echo "MUnit Test"
            }
        }

        stage('Deploy') {
            steps {
				bat 'mvn -U -V -e -B -DskipTests deploy -DmuleDeploy -Dusername=kronos9029 -Dpassword=Kronos9029@!'
            }
        }
    }
}