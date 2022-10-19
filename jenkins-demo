pipeline {
    agent none
    stages {
        
        stage('non-parallel-stage') {
                    agent {
                        label "Built-In-Node"
                    }
                    steps {
                        echo 'this executes first'
                    }
        } 
        
        stage('run tests') {
            parallel {
                stage('test on windows') {
                    agent {
                        label "windows-node"
                    }
                    steps {
                        echo "task on agent"
                    }
                }
                stage('test on master') {
                    agent {
                        label "Built-In-Node"
                    }
                    steps {
                        echo "task on master"
                    }

                }
            }
        }
    }
}
