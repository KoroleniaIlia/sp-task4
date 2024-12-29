pipeline {
    agent any
    
    stages {
        stage('Checkout') {
        steps {
                git url: 'https://github.com/KoroleniaIlia/sp-task4.git', credentialsId: 'add credentialsId'
            }
        }
        
        stage('Build') {
        steps {
            bat '"C:\\Program Files\\Microsoft Visual Studio\\2022\\Preview\\MSBuild\\Current\\Bin\\MSBuild.exe" korolenia-test.sln /t:Build /p:Configuration=Release'
            }
        }
            
        
        
        stage('Test') {
        steps {
            bat '"E:\GARBAGE\sys_prog_3_course\lab4\korolenia-test\x64\Debug\\korolenia-test.exe" --gtest_output="xml:test_report.xml"'
            }
        }}
        
        post {
    always {
        // Publish test results using the junit step
        junit 'korolenia-test.xml' // Specify the path to the XML test result files
    }
}
}