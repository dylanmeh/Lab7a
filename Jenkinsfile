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
        stage('Main') {
            steps {
                script {
                    def properties = readProperties(file: 'build.properties')
                }
            }
        }
        stage('echo value1') {
            sh "echo 'print ${properties["key1"]}'"
        }
    }
}