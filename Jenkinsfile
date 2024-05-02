 pipeline {
        agent any
        environment
        {
            Directory_Path = 'C:/ProgramData/Jenkins/.jenkins/workspace/SIT753'
            TESTING_ENVIRONMENT  = 'Sit753 test Evironment'
            PRODUCTION_ENVIRONMENT =  'Prashants production Environment'
        }
        stages {
            stage('Build') {
                steps {
                    echo "Fetch The Source code from ${env.Directory_Path}"
                }
            }
            stage('Test') {
                steps {
                    echo 'Unit Tests'
                    echo 'Integration Tests'
                }
            }
            stage('Code Quality Stage') {
                steps {
                    echo 'Check the Quality Of the Code'
                    
                }
            }
            stage('Deploy') {
                steps {
                    echo "Deploy the Application to the Testing Envitonment ${env.TESTING_ENVIRONMENT}"
                   
                }
            }
            stage('Approve') {
                steps {
                    sleep 10
                }
            }
            stage('Deploy To Production ') {
                steps {
                    echo "Deploy to production Environment ${env.PRODUCTION_ENVIRONMENT}"
                }
            }
        }
    }