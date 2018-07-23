def jenkins_path= "/var/lib/jenkins"

node {

    stage('scm'){
        checkout scm
        sh "pwd"
    }
    
    stage('git'){
      sh "branchname=`git branch -a | grep remotes/origin/PR`"
      sh "git checkout $branchname"
      sh "cat test.txt"
    }
    
  
   stage('serve'){
    sh "npm install"
    sh "ng serve --host 0.0.0.0 &"
    sh "sleep 60"
    sh "kill `ps |grep ng |awk '{print \$1}'`"
  }

    
}
