pipeline{

    agent any

    // tools {nodejs "node"}

    parameters{
        string(name: "SPEC", defaultValue: "cypress/integration/**/**", description: "Enter the script path that you want to execute")
        choice(name: "BROWSER", choices:['chrome'], description:"choose the browser where you want to execute your script")
    }
    
    stages{

        // stage('Install Dependencies'){
        //     steps{
        //         dir('docker/build/'){
        //         // sh 'npm install'
        //         }
        //      }
        // }

        // stage('Building'){
        //     steps{
        //         dir('docker/build/'){
        //         sh 'ls'
        //         sh './deploy.sh -n -w -i'
        //        }
        //     }
        // }

        stage('Testing'){
            steps{
                // dir('nx/oryx/cypress/integration/'){
                // sh 'ls'
                // sh 'npm install'
                sh 'ls'
                sh "npx cypress run --browser chrome --spec cypress/integration/**/**"
                // }
                
            }
        }

        // stage('Deploying'){
        //     steps{
        //         echo "Deploy the Application"
        //     }  
        //  }

    }
    post{
        always{
            publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'cypress/reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
        }
    }
}
