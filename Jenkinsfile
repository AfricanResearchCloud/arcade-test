pipeline {
  agent any
  stages {
    stage('Transfer') {
      steps {
        echo 'Transfering...'
      }
    }
    stage('Data Management & Averaging') {
      steps {
        echo 'Calibrating...'
      }
    }
    stage('Polarization & Cross Calibration') {
      steps {
        echo 'Imaging...'
      }
    }
    stage('Flagging') {
      steps {
        parallel(
          "Flagging": {
            echo 'Commiting...'
            
          },
          "More Flagging": {
            sh 'docker run casapy'
            
          }
        )
      }
    }
    stage('SelfCal') {
      steps {
        echo 'SelfCal'
      }
    }
    stage('DDE Calibration / Peeling') {
      steps {
        echo 'DDE Calibration / Peeling'
      }
    }
  }
}