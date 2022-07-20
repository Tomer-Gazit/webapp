pipeline {
agent none
stages {
  stage('Clean') {
    steps {
      cleanWs()
    }
  }
  stage('Cloning Git') {
    steps {
      sh git clone https://github.com/Tomer-Gazit/webapp.git
    }
  }
  stage('Building Image') {
    steps {
      script {
        sh cd webapp
	sh docker build -t my-apache2
      }
    }
  }
  stage('Run Container')
    steps {
    sh docker run -dit --name my-running-app -p 8085:80 my-apache2
    }
  }
}
