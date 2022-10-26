Tips KUB AutoCompletion 
##  Activer l'auto-complétion pour bash dans le shell courant, le paquet bash-completion devant être installé au préalable
```source <(kubectl completion bash) ```

## Ajouter l'auto-complétion de manière permanente à votre shell bash
```echo "source <(kubectl completion bash)" >> ~/.bashrc```

## Déclarer un alias pour kubectl qui fonctionne aussi avec l'auto-complétion :
```alias k=kubectl```   
```complete -o default -F __start_kubectl k```


## Voir toutes les ressources d'un namespace
```k get all -n production```

## Voir  le descriptif d'un service (la nodeport)
```k describe -n production service service-nodeport-web```


## InGress
Mecanisme qui fait le lien entre l'urlet le service de type Cluster IP  
Il s'appuie sur des ingress rules  
IngressController : Firewall a la porte des namespace  
Permet de faire du reverseProxy en se basant sur le contest http://<url>/toto et http://<url>/titi

https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/  

https://kubernetes.github.io/ingress-nginx/deploy/#provider-specific-steps  
```
k get ingress
 ```
  
  
## Creation d'un namespace
```
k get ns 
k get namespace
k get ns 
k get all -n default // pour connaitre les ressources sous le namespace

  ```

## Different type de service 
```
Service de typ NodePort : 
Permet d'exposer son pod à l'exterieur du cluster 
3 ports : 
  - NodePort : le port disponible deouis l'exterieur , le port du node , valeur comprise entre 3000 et 32000
  - Port : le port interne qui pourra etre utiliser par les applications à l'interieur du namespace
  - TargetPort : le port cible, le port exposé par le container
 
 Service de typeCLusterIP :
 Permet d'exposer son appliation uniquement à l'interieur du cluster.
 2 ports : 
  - Port : le port interne qui pourra etre utiliser par les applications à l'interieur du namespace
  - TargetPort : le port cible, le port exposé par le container
 
 Service de type LoadBalancer 
 Service pour associer le service a un loadbalancer provider 
 
  ```
## Voir les logs lors d'un probleme 
Regare au niveua des logs du container : ```kubectl logs container```
Regarder au niveau des evenements :  ```kubectl get events --all-namespaces  --sort-by='.metadata.creationTimestamp'```
