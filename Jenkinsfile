pipeline{
    agent any
    stages{
        stage('clone repo'){
            steps{
                git credentialId : "Demotoken", url : 'https://github.com/RakhiGpt/jen.git' , branch : 'main'
            }

        }
        stage('dependency'){
            steps{
                bat '''
                python -m venv venv
                call venv\\Script\\active
                python -m pip install --upgrade pip
                pip install pytest
                '''
            }

        }
        stage('test'){
            steps{
                bat '''
                call venv\\Script\\active
                pytest testfile.py
                '''
            }
        }
        stage('deploy'){
            steps{
                bat '''
                call venv\\Script\\active
                python hello.py
                '''
            }
        }
    }
}


