
def mylabel = "worker-${UUID.randomUUID().toString()}"

pipeline {

  agent {
    kubernetes {
      label mylabel
      defaultContainer 'kubectl'
      yaml """
        apiVersion: v1
        kind: Pod
        metadata:
        labels:
          component: ci
        spec:
          # Use service account that can deploy to all namespaces
          containers:
          - name: kubectl
            image: gcr.io/cloud-builders/kubectl
            #image: marketplace.gcr.io/google/ubuntu1804
            command:
            - cat
            tty: true
            resources:
              limits:
                cpu: 100m
                memory: 600Mi
              requests:
                cpu: 100m
                memory: 300Mi
      """
    }
  }

  stages {


    
  }//stages

}//end pipeline      
