 pipeline {
        agent any
        environment
        {
            Directory_Path = 'C:/ProgramData/Jenkins/.jenkins/workspace/SIT753'
                TESTING_ENVIRONMENT  = 'Sit753 test Evironment'
                PRODUCTION_ENVIRONMENT =  "Prashants production Environment"
                logfiletest = "${env.WORKSPACE}\\testing.log"
                logfilesecurity = "${env.WORKSPACE}\\securityscan.log"
                email = "prashanthvpatill@gmail.com"
        }
        stages {
            stage('Build') {
                steps {
                    echo "Fetch The Source code from ${env.Directory_Path}"
                }
            }
             stage('Unit and Integration tests') {
            steps {
                echo "Running Integration and Unit Tests"
                script {
                    bat "echo Initiating Unit test  using TestNG > ${env.logfiletest}"
                    bat " echo Unit test is comlpleted and adding results to log file >>${env.logfiletest}"
                    bat " echo Initiating Integration tests using Selenium   >>${env.logfiletest}"
                    bat " echo  Integration tests completed saving result to log file    >>${env.logfiletest}"
                    

                }
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