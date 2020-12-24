node
  {
    stage("Check Out")
    {
          checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'adf05bd0-541b-40d0-b33f-a6aae4f95c10', url: 'https://github.com/princy1612/htmlreport.git']]])
          
          echo "current build number: ${currentBuild.number}"
          echo "previous build number: ${currentBuild.previousBuild.getNumber()}"    
          
          sh 'npm install'
    }
    stage("Execution of Code")
    {
        sh '''cd C:\\Users\\40010003\\Desktop\\JS-Jasmineminiproject-main\\Jasmine Frame Work\\src
         node Bank.js'''
       
    }
    stage("Installation of Jasmine")
    {
        sh '''cd C:\\Users\\40010003\\Desktop\\JS-Jasmineminiproject-main\\Jasmine Frame Work\\Spec
          npm install jasmine-node
           '''
    }
    stage("Execution of Test Code")
    {
        sh '''cd C:\\Users\\40010003\\Desktop\\JS-Jasmineminiproject-main\\Jasmine Frame Work
        npx jasmine init
            '''
        sh '''cd C:\\Users\\40010003\\Desktop\\JS-Jasmineminiproject-main\\Jasmine Frame Work
        npx jasmine Spec/Bank.js
            '''
    }
    stage("HTML Report")
    {
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'C:\\Users\\40010003\\Desktop\\JS-Jasmineminiproject-main\\Jasmine Frame Work', reportFiles: 'SpecRunner.html', reportName: 'HTML Report', reportTitles: ''])
    }
 
}
