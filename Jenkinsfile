pipeline {

    agent any
    
    stages {
         stage ('Compile Stage') {
            steps {
                 bat 'mvn -f Registration_Backend/pom.xml clean install'
                 bat 'cd Registration_Frontend/build && npm run build'
            }
         }
        stage ('Deploy Stage') {
            steps {
                 bat 'start java -jar Registration_Backend/target/Registration_Backend.jar'
                 bat 'cd Registration_Frontend && cd build && start python -m http.server 8884'
            }
        }
        
    }
}
