pipeline {
    agent any
        environment { 
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }
    
    stages {
        stage('Test') {
            steps {
               sh '''
                  date 
                  pwd 
                  cal
                  '''
            }
        }    
      stage('Enviroment Variable ') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${DISABLE_AUTH}"'
                sh  'echo "${DB_ENGINE}"'
            }
        }  
      stage('Deploy on Test') {
            steps {
             echo 'Deploy on Test'  
            }
        }  
      
      stage('Approve"?') {
           steps {
            input message: "Please Approve", ok: 'Approve'
        }
      }
        
     stage('Deploy on Prod') {
            steps {
                echo 'Deploy on Prod'
            }
        }     
        
    }
    post {
     always {
        echo "========I will always say hello again ========"
    }
       failure {
           echo "========Failure======"
       }
       success {
          echo "The Pipeline success"
    }
    }
}

    
