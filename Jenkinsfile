//git credentials
def git_auth = "571f959b-ec48-4ec9-819c-d3a25a99fffb"
//git url
def git_url = "git@github.com:MyNetdisk/blog.git"
node {
    try{
        stage('pull the code') {
            checkout([$class: 'GitSCM', branches: [[name: "*/${branch}"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: "${git_auth}", url: "${git_url}"]]])
        }
    }catch(e){
        throw e
    }finally{
        // 邮件发送功能
        // emailext( subject: '构建通知：${PROJECT_NAME} - Build # ${BUILD_NUMBER} - ${BUILD_STATUS}!', body: '${FILE,path="email.html"}', to: 'coderlife@foxmail.com' )
    }
}