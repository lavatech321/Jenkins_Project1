pipeline {
         agent any
         stages {
                 stage('One') {
                 steps {
                     echo 'This is stage One message'
                 }
                 }
                 stage('Two') {
                 steps {
                    input('This is stage two, Do you want to proceed?')
                 }
                 }
                 stage('Three') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                       echo "This is stage 3"
                 }
                 }
                 stage('Four') {
                 parallel { 
                            stage('Unit Test') {
                           steps {
                                echo "Running the unit test..."
                           }
                           }
                            stage('Integration test') {
                
                              steps {
                                echo "Running the integration test..."
                              }
                           }
                           }
                           }
              }
}
