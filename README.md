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
