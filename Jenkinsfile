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
            stage('Code Analysis') {
                steps {
                    echo 'Initiating Code Analysis using CodeClimate '
                    
            }
        }
            stage('Security Scan') {
                steps {
                    echo "Running Security Scans using Nikto"
                script{
                    bat "echo Initiating Security Scan using Nikto > ${env.logfilesecurity}"
                    bat "echo Security Scan Completed and adding results to security log file >> ${env.logfilesecurity}"
                }
            }
            stage('Integration tests on Staging ') {
                steps {
                    echo "Initiating Integration tests on staging to ensure application is funtioning as expected to in production like environment"
                }
            }
            stage('Deploy To Production ') {
                steps {
                    echo "Deploying on Production Server in Amazon AWS EC2 instance"
                }
            }
        }
    }