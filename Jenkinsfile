pipeline {

    /* 1️⃣ Docker agent definition */
    agent {
        docker {
            image 'node:18-alpine'
            args '-u root:root'
        }
    }
    stages{
        stage('Directory and File Operations') {
    steps {
        sh '''
          echo "Creating directory"
          mkdir labeeqsdir

          echo "Renaming directory"
          mv labeeqsdir labeeqdir_renamed

          echo "Creating file inside directory"
          touch labeeqdir_renamed/info.txt

          echo "Listing contents"
          ls -R labeeqdir_renamed
        '''
    }
}
}
}
