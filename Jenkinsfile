pipeline
{
    stage('Deploy') {
      steps {
        // script { STAGE=env.STAGE_NAME + " :k8s:" }
        script { DIGEST=sh(script: "docker manifest inspect docker.io/library/nginx:latest --verbose | jq ".Descriptor.digest"")}
        sh "echo ${DIGEST}"
        // sh "/usr/local/bin/argocd app list -l argocd.argoproj.io/service=${env.PROJECT}-stage -o name | xargs -I {arg} argocd app set {arg} -p global.tag=${env.TAG}"
        // sh "/usr/local/bin/argocd app sync -l argocd.argoproj.io/service=${env.PROJECT}-stage"
      }
    }
}
