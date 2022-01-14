def props = [:]
props = readProperties(file: 'build.properties')
pipeline {
    agent {
        kubernetes {
            yaml '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: shell
    image: ubuntu
    command:
    - sleep
    args:
    - infinity
'''
            defaultContainer 'shell'
        }
    }
    stages {
        stage('echo value1') {
            steps {
                script {
                    echo "print ${props["key1"]}"
                }    
            }            
        }
        stage('echo value2') {
            steps {
                script {
                    echo "print ${props["key2"]}"
                }       
            }        
        }
    }
}