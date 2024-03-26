pipeline{
    agent any
    environment {
    FIREBASE_DEPLOY_TOKEN = credentials('firebase-token-ce2')
    }

 stages{
        stage('Building'){
            steps{
           // sh 'npm install -g firebase-tools'
                echo 'Building...'
            }
        } 
        stage('Testing Environment'){
            steps{
            sh 'firebase deploy -P stand-32ace --token "$FIREBASE_DEPLOY_TOKEN"'
            input message: 'After testing. Do you want to continue with Staging Environment? (Click "Proceed" to continue)'
            }
        } 
        stage('Staging Environment'){
            steps{
             sh 'firebase deploy -P class-stage-1 --token "$FIREBASE_DEPLOY_TOKEN"'
             echo  'Building'
            }
        } 
        stage('Production Environment'){
            steps{
            sh 'firebase deploy -P production-ce --token "$FIREBASE_DEPLOY_TOKEN"'
            echo 'Building'
            }
        } 
    }

}
