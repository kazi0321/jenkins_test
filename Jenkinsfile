def jenkins_path= "/var/lib/jenkins"
def angular_path = "${jenkins_path}/angular"
def clone_path = "${angular_path}/test_app"

node {

    stage('scm'){
        checkout scm
    }

  stage('git'){
      dir("${angular_path}"){
    sh "rm -rf *"
    sh "git clone https://github.com/kazi0321/test_app.git"
  }
  }
  
  stage('serve'){
      dir("${clone_path}"){
    sh "npm install"
    sh "ng serve --host 0.0.0.0 &"
    sh "sleep 60"
    sh "kill `ps |grep ng |awk '{print $1}'`"
  }
  }

    
}
