node {
    def app
    def IMAGETAG
    def scmVars
    def gitCommit
    def today = new Date()
    def APPENV
    def curBranch

    stage('Clone repository') {     
        scmVars = checkout scm

        gitCommit = scmVars.GIT_COMMIT.substring(0, 10);
        curBranch = scmVars.GIT_BRANCH

        sh "echo GIT_BRANCH"
        sh "${curBranch}"

        if (curBranch.indexOf("feature/") > -1) {
            sh "echo this is feature branch"
        } else if (curBranch.indexOf("release/") > -1) {
            sh "echo this is release branch"
        }
        else {
            sh "echo other branch"
        }
    }
}
