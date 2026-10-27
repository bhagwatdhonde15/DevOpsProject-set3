pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'feature/set3-update',
                    url: 'https://github.com/bhagwatdhonde15/DevOpsProject-set3.git'
                echo 'Checkout completed successfully'
            }
        }

        stage('Build') {
            steps {
                sh 'javac HelloWorld.java'
                echo 'Build completed successfully'
            }
        }

        stage('Test') {
            steps {
                sh '''
                    java HelloWorld > output.txt
                    cat output.txt
                    grep -q "Hello from DevOps!" output.txt
                    grep -q "Set 3 - Git and Linux Practical" output.txt
                    grep -q "Feature branch update successful!" output.txt
                '''
                echo 'All tests passed successfully'
            }
        }
    }
}
