pipeline {
     agent any
    parameters {
        booleanParam(name:'project', defaultValue: true, description:'this paramater help you to know project name')
        choice(name: 'namespace', choices:['dev','prod','stage'], description: '' ) 
    }

    stages {
        stage('check') {
            steps {
                echo "checking your code"
                echo "${params.namespace}"
               
            }
        }

        stage('test') {
            when {
                expression{
                    params.project != false
                }
            }
            steps {
                echo "testing your app" 
            }
        }
        
        stage('deployment') {  
            steps {
                echo "Your code is deployed right now"
                echo "This build number $BUILD_NUMBER"
                echo "This build ID $BUILD_ID"
                echo "This Branch Name: $BRANCH_NAME"
            }
        }    
    }

}