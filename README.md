# k8s-webforce3

## Check
```shell script
  kubectl get nodes
  kubectl get node
  kubectl get node -o wide:

## Deployment example
  kubectl create deployment nginx --image=nginx
  kubectl get deployments
  kubectl describe deployment nginx
  kubectl get events
  kubectl get deployment nginx -o yaml 
  kubectl get deployment nginx -o yaml > first.yaml
```

......


# k create create -f first.yaml
# kubectl get deployment nginx -o ymal >second.ymal
# kubectl create deployment two -- image=nginx --dry-run -o yaml (affiche le contenu d'execution mais ne l'execute pas)  
# kubectl get deployment nginx --export -o json
# kubectl get deployment nginx --export -o yaml
# k expose -h
# kubectl expose deployment/nginx
#kubectl replace -f first.yaml
#kubectl get deploy,pod
#kubectl expose deployment/nginx
#kubectl get svc nginx (svc service)
#k get ep nginx (ip)
#curl + ip (permet de voir ce qui a "dans l'exemple html")
#k get pod  (permet d'avoir le "name" du pod)
#kubectl describe pod nginx-xxxx | grep Node: 
#k get pod -o wide (donne l'adresse du noeud)
#kubectl scale deployment nginx --replicas=3 (permet de crée  "dans l'exemple  de trois serveurs)
#k get deploy nginx (permet de voir les 3 serveurs en charge "ils sont démarré")
#k get ep nginx (permet de voir les "end points")
#kubectl exec nginx-xxxx -- printenv |grep KUBERNETES (Permet de voir l'etat du pod)
#kubectl delete svc nginx (detruit le service)
#kubectl expose deployment nginx --type=LoadBalancer (recrée port pour le monde exterieur est superier a :30000)
#k get svc -A (info global)

# ssh -L 12000:51.68.5.165:30580 etudiant@localhost (exemple ssh tunnel, pour diffcultes avec l'interface graphique)

# kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}' ) 
(permet de crée le jeton)

#kubectl create deployment hog --image vish/stress (stress test)
#k get deployment hog 
#k describe deployment hog
#kebectl get deployment hog --export -o yaml > hog.yalm 





