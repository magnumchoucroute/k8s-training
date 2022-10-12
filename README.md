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
