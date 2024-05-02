pipeline {
        agent any
        environment
        {
          logfiletest = ${env.WORKSPACE}/testing.log"
          logfilesecurity = "${env.WORKSPACE}/securityscan.log"
          email = "prashanthvpatill@gmail.com"
        }
        stages {
            stage('Build') {
                steps {
                    echo "Building Code from Maven Automation Tool "
                }
            }
            stage('Test') {
                steps {
                    echo "Running Integration and Unit Tests"
                    script {
                    sh """
                        echo "Starting unittests using TestNG ">logfiletest
                    """
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
