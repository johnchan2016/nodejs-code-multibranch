node {
    def app
    def IMAGETAG
    def scmVars
    def gitCommit
    def today = new Date()
    def APPENV

    stage('Clone repository') {     
        scmVars = checkout scm

        gitCommit = scmVars.GIT_COMMIT.substring(0, 10);

        sh "echo GIT_BRANCH"
        sh "${scmVars.GIT_BRANCH}"

        if (scmVars.GIT_BRANCH.indexOf("/feature/") > -1) {
            sh "echo 'this is feature branch'"
        } else if (scmVars.GIT_BRANCH.indexOf("/release/") > -1) {
            sh "echo 'this is release branch'"
        }
        else {
            sh "echo 'other branch'"
        }
    }
}
