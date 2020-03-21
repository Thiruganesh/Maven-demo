pipeline {
    agent any
    stages {
stage('scm') {
steps {
    git 'https://github.com/Thiruganesh/Maven_demo.git'
    }
}
    stage('build') {
    steps {
        withMaven(maven : 'mymaven'){
        bat "mvn clean install"
    }
    }
}
     stage('junit') {
steps {
    junit healthScaleFactor: 10.0, testResults: '**/gameoflife-web/target/surefire-reports/*.xml'
    }
} 
    stage('deploy') {
steps {
    bat 'copy "C:\\DEVOPS\\Jenkins\\workspace\\Maven-demo-project\\gameoflife-web\\target\\gameoflife.war "C:\\DEVOPS\\apache-tomcat-9.0.33\\webapps"'
    }
}
}
}
