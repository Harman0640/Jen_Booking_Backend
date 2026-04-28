pipeline{
    agent any
    environment{
        VENV = 'venv'// Define any environment variables if needed
    }
    stages{
        stage('Clone Repository'){
            steps{
                sh 'git url: https://github.com/Harman0640/Jen_Booking_Backend.git' ,branch: 'main'
            }
        }
        stage('install dependency'){
            steps{
                sh '''
                sudo apt install python3-venv -y
                python3 -m venv $VENV
                '''
            }
        }
        stage('Run'){
            steps{
                sh '''
                $VENV/bin/pip install -r requirements.txt
                $VENV/bin/uvicorn unified_main:app --host 0.0.0.0 --port 8000 
                '''
            }
        }
    }
}