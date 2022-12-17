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

        if (curBranch.indexOf("feature/") > -1 || curBranch.indexOf("bugfix/") > -1) {
            APPENV = "dev"
        } else if (curBranch.indexOf("release/") > -1) {
            APPENV = "uat"
        } else if (curBranch.indexOf("main/") > -1 || curBranch.indexOf("hotfix/") > -1) {
            APPENV = "prd"
        } else {
            process.exit()
        }
        
    }
}
