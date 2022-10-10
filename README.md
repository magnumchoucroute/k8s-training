Tips KUB AutoCompletion 
##  Activer l'auto-complétion pour bash dans le shell courant, le paquet bash-completion devant être installé au préalable
```source <(kubectl completion bash) ```

## Ajouter l'auto-complétion de manière permanente à votre shell bash
```echo "source <(kubectl completion bash)" >> ~/.bashrc```

## Déclarer un alias pour kubectl qui fonctionne aussi avec l'auto-complétion :
```alias k=kubectl```   
```complete -o default -F __start_kubectl k```
