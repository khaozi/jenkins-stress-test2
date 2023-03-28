#!groovy
node('master') {

    stage('stage1: Git checkout main branch') {
        sh "git clone https://github.com/khaozi/jenkins-stress-test2.git; cd jenkins-stress-test2 ;git pull origin main"
    }

    stage('stage2: and delete old versions and calculations') {
        // sh "rm -rf ${WORKSPACE}@script/*/migrations"
        echo "copy and delete old versions"
        sh 'sum=0;for i in {1..100}; do echo sum=$((sum+i)); echo ${sum} ;done'

    }

    stage('stage3: copy to target host and calculations'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "copy to target host"
        sh "sum=0;for i in {1..100}; do echo sum=$((sum+i)); echo $sum ;done"
    }

    //stage('Deploy:makemigrations') {
    //    sh "ansible-playbook ${WORKSPACE}/backend/test_platform.yml --tags='makemigrations' -e \"host=172.26.129.143\""
    //}
    //stage('Deploy:migrate') {
    //    sh "ansible-playbook ${WORKSPACE}/backend/test_platform.yml  --tags='migrate' -e \"host=172.26.129.143\""
    //}
    stage('stage4: pre-restart check env'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "stage 4: pre-restart check env"
    }
    stage('stage5: pre-restart check md5sum'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "stage5: pre-restart check md5sum"
    }
    stage('stage 6: scp oldfiles to remote'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "stage 6: scp oldfiles to remote"
    }
    stage('stage7: check remote md5sum'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "check remote md5sum "
    }
    stage('stage8: roll-upgrade'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "stage8: roll-upgrade"
    }
    stage('stage9: check configfile'){
        // sh "scp -r ${WORKSPACE}/backend/* root@172.26.129.143:/opt/test-platform/test-platform/backend/"
        echo "stage9: check config file"
    }
    stage('stage 10: Deploy:restart') {
        // sh "ansible-playbook ${WORKSPACE}/backend/test_platform.yml  --tags='restart' -e \"host=172.26.129.143\""
        echo  "deploy restart test"
    }
    //stage('Deploy:curl_test') {
    //    sh "ansible-playbook ${WORKSPACE}/backend/test_platform.yml  --tags='curl_test' -e \"host=172.26.129.143\""
    //}
}

