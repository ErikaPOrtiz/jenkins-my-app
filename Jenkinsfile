pipeline {
    agent any
    stages {
        // stage('Build') {
        //     agent{
        //         docker{
        //             image 'node:20.16.0-alpine'
        //             reuseNode true
        //         }
        //     }
        //     steps {
        //         sh '''
        //         ls -la
        //         node --version
        //         npm --version
        //         npm install
        //         npm run build
        //         ls -la
        //         '''
        //     }
        // }
        // stage('Test'){
        //     agent{
        //         docker{
        //             image 'node:20.16.0-alpine'
        //             reuseNode true
        //         }
        //     }
        //     steps{
        //         sh'''
        //             test -f build/index.html
        //             npm test
        //         '''
        //     }
        // }    
        stage('Deploy'){
            agent{
                docker{
                    image 'amazon/aws-cli'//change to AWS
                    reuseNode true
                    args '--entrypoint=""'
                }
            }
        
        steps{
            sh'''
                asw --version 
                asw s3 ls
             
            '''
            }
        }
    }
}
