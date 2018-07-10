def jenkins_path= "/var/lib/jenkins"
def angular_path = "${jenkins_path}/angular"

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
      dir("${angular_path}"){
    sh "cd test_app"
    sh "npm install"
    sh "ng serve --host 0.0.0.0"
  }
  }

}
