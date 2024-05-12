pipeline {

    agent  any 

    triggers {
        pollSCM '* * * * *'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                apt install python3 -y
                python3 --version
                pip3 install -U pytest
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}