pipeline
{
    agent {
        label '1C'
    }

    environment {
        envString = 'true'
    }

    post {
        always {            
            //allure includeProperties: false, jdk: '', results: [[path: 'out/syntax-check/allure'], [path: 'out/smoke/allure/']]
            //junit allowEmptyResults: true , testResults: 'out/smoke/junit/*.xml'
            bat "echo hello"
        }

         failure {
             bat "echo failure"
         }

         success {
             bat "echo succes"
         }

    }

    stages {
         stage("Build test base") {
             steps {                
                bat "chcp 65001\n echo Первый этап сборки"
                 //bat "chcp 65001\n vrunner init-dev --dt C:\\jenkins\\template\\dev.dt --src C:\\repo\\jenkins_repo\\src"
                bat "vrunner init-dev --ibconnection /Fd:\\git\\kotov_dz12\\build\\ib --dt d:\\Distr\\Jenkins\\tmp\\dev.dt --db-user ci-bot --src d:\\git\\kotov_dz12\\src"
             }
         }       
        // stage("Syntax check") {
        //     steps {                
        //         bat "chcp 65001\n vrunner syntax-check"
        //     }
        // }
        // stage("Smoke tests") {
        //     steps {
        //         script {
        //             try {
        //                 bat "chcp 65001\n vrunner xunit"
        //             }
        //             catch(Exception Exc) {
        //                 currentBuild.result = 'UNSTABLE'
        //             }
        //         }                
        //     }
        // }
        // stage("Vanessa") {
        //     steps {
        //         script {
        //             try {
        //                 bat "chcp 65001\n vrunner vanessa"
        //             }
        //             catch(Exception Exc) {
        //                 currentBuild.result = 'UNSTABLE'
        //             }
        //         }                
        //     }
        // } 
        //stage("Sonar") {
        //    steps {
        //        script {
        //            scannerHome = tool 'sonar-scanner'
        //        }
        //        withSonarQubeEnv("sonar") {
        //            bat "chcp 65001\n ${scannerHome}/bin/sonar-scanner -D sonar.login=sqp_ff1f8486e5db41bcca28e81970a89395690440a4"
        //        }                
        //    }
        //} 
    }
}