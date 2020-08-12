# Dashboard
https://github.com/kubernetes/dashboard
https://docs.aws.amazon.com/eks/latest/userguide/dashboard-tutorial.html

+ changes:
 - We are using alternative to get access HTTP. So compare with recommended to check changes
 - ADD Clusterrolebinding-cadmin, Only for dev purpose, please get token and pass it to admin

How To Run:
// - kubectl apply -f ./dashboard/dashboard.yaml
// - kubectl apply -f ./dashboard/ingress.yaml
 - kubectl apply -f ./dashboard/clusterrolebinding-admin.yaml
 - kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep kubernetes-dashboard | awk '{print $1}')

# App

How To Run:
 - kubectl apply -f ./service/app.yaml --record=true
 - // if it fails: kubectl rollout undo deployment any-service -n ${namespace}
 - // if it fails and points to revision 1: kubectl rollout undo deployment any-service --to-revision=1 -n ${namespace}
 - //check history: kubectl rollout history deployment -n ${namespace}



#TODO: 
 - Jenkins commands
 - Services ECR: https://docs.aws.amazon.com/AmazonECR/latest/userguide/ECR_on_EKS.html
 ...

https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-kubernetes-dashboard/
------------
https://docs.aws.amazon.com/eks/latest/userguide/dashboard-tutorial.html
https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-kubernetes-dashboard/
http://a48751136934f41c4aefe3fa69e6a434-757ad43d17f6e9af.elb.us-west-2.amazonaws.com/dashboard/
https://aws.amazon.com/premiumsupport/knowledge-center/eks-kubernetes-dashboard-custom-path/
https://docs.aws.amazon.com/eks/latest/userguide/dashboard-tutorial.html


---
docs
https://aws.amazon.com/premiumsupport/knowledge-center/eks-kubernetes-dashboard-custom-path/
https://github.com/helm/charts/issues/5007
https://vividcode.io/disable-authentication-and-https-in-kubernetes-dashboard/
https://github.com/kubernetes/dashboard/tree/master/aio/deploy
https://www.google.com/search?client=firefox-b-d&ei=nXDoXqDFBPHD5OUPlOuUuAU&q=configmaps+is+forbidden%3A+User+serviceaccount%3Akubernetes-dashboard+%229090%22&oq=configmaps+is+forbidden%3A+User+serviceaccount%3Akubernetes-dashboard+%229090%22&gs_lcp=CgZwc3ktYWIQAzoHCAAQRxCwA1Cfb1iMoAFg1aIBaARwAHgAgAFziAGpDZIBBDE1LjOYAQCgAQGqAQdnd3Mtd2l6&sclient=psy-ab&ved=0ahUKEwjgh-OC5IXqAhXxIbkGHZQ1BVcQ4dUDCAs&uact=5