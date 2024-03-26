pipeline{
    agent any
    environment {
    FIREBASE_DEPLOY_TOKEN = credentials('Firebase-Token')
    }

 stages{
       
        stage('Testing Environment'){
            steps{
            sh 'firebase deploy -P stand-32ace --token "$FIREBASE_DEPLOY_TOKEN"'
            
            }
        } 
        stage('Staging Environment'){
            steps{

          sh 'firebase deploy -P sterling-11494 --token "$FIREBASE_DEPLOY_TOKEN"'

         

             echo  'Building'
            }
        } 
        stage('Production Environment'){
            steps{
            sh 'firebase deploy -P project1-fbe89 --token "$FIREBASE_DEPLOY_TOKEN"'
            echo 'Production'
            }
        } 
    }

}
