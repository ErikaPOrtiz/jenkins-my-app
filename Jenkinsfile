pipeline {
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
            withCredentials([usernamePassword(credentialsId: 'my-temp', passwordVariable: 'AWS_SECRET_ACCES_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) 
            {
                sh'''
                    aws --version 
                    aws s3 ls
                
                '''
            }
        }
    }
}

}
