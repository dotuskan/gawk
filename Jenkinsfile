pipeline {
    agent any
    
        
    stages {
        stage("clean"){
            steps {
                sh '''#!/bin/bash
                make clean
                '''
            }
        }
        
        stage("bootstrap"){
            steps {
                sh '''#!/bin/bash
                ./bootstrap.sh
                '''
            }
        }

        stage("configure"){
            steps {
                /*Since Jenkins's build directory's name contain space character, quotes must be added to ends of
                path*/
                sh '''#!/bin/bash
                bash -c "./configure --prefix='${PWD}/outputs'"
                '''
                
            }
        }

        stage("install"){
            steps {
                sh '''#!/bin/bash
                make install
                '''
            }
        }

        stage("check"){
            steps {
                sh '''#!/bin/bash
                make check
                '''
            }
        }
    }
}
