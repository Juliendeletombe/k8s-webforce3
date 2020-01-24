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
#kubectl expose deployment nginx --type=LoadBalancer (recrée port pour le monde exterieur est superieur a :30000)
#k get svc -A (info global)

# ssh -L 12000:51.68.5.165:30580 etudiant@localhost (exemple ssh tunnel, pour diffcultes avec l'interface graphique)

# kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}' ) 
(permet de crée le jeton)

#kubectl create deployment hog --image vish/stress (stress test)
#k get deployment hog 
#k describe deployment hog
#kebectl get deployment hog --export -o yaml > hog.yalm 


#k replace -f hog.yam1
#k get po
#k logshog-xxxxxx
#k delete deployment.apps hog
#k create -f hog.ymal
# get pod
#logs hog -xxx-xxx


# kubectl scale deployment hog --replicas=10 (dans l'exemple de notre stress test la ram est insuffissante)
# j'ai donc remis 3 machine apres le test.

# k delete deploy hog (destruction du deploiment , liberationd e la ram)

# Name spaces ## Namespaces

#kubectl create namespace low-usage-limit (création)
#k gget namespace (afficher les namespace)
# dans l'ide créer un fichier lowressources low-resource-range.yaml

#k --namespace=low-usage-limit create -f low-resource-range.yaml 
#k get LimitRange
# k get LimitRange -A

#k --namespace low-usage-limit create deployment limited-hog -- image vish/stress (deploiment du stress test dans hog)
#kubectl -n low-usage-limit get pods 

#k -n low-usage-limit get pod limited-hog-5c8d494fc5-6nr5n -o yaml

#history > history-1.txt (permet d'avoir une liste de toute les commandes taper en texte)

#k get rs (pour voir les replicaset)
#k get rs -A (pour les voir tous)
#k -n low-usage-limit delete deploy limited-hog  (supression le deploiment limited-hog)

#k create -f rs.yaml
#k describe rs rs-one
#k get pods
#k delete rs rs-one --cascade=false (supprimer uniquement les repliques)
#k k describe rs rs-one (verifie si il existe encore , non)
#k get pods
# kubectl create -f rs.yaml (recrée les replicas)
#k get rs,pod (afficher les replicas  et pods)

#(isoler un pod du réplica set , dans l'idée pour travailler dessus sans impacter le prod 
#exemple suite a un disfonctionnement

# k edit pod rs-one-xxxx (entre a chaud pour changer les caracteristique du pod) 
#(pour quitter avec save !wq , :q! quitter sans save)
#k get po -L system (permet de voir meme les pod isolé, ce que la commande k get rs ne donne pas)
#kebectl describe po rs-one-dfsbk | grep Image: 













