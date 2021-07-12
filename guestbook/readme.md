# GitOps & ARGOCD

CONTENTS OF THIS FILE
---------------------

Deploy di esempio in un processo GitOps:

      1) esempio di applicazione semplice (guestbook)
      2) esempio di deploy di un operator (hazelcast)

 
Comandi utili ARGO
-------------

1. Da linea di comando, effettuare la login su ArgoCD

   ```
   argocd login localhost:8001 --username admin
   ```

4. Creare la propria applicazione su ArgoCD

   * Per il deploy dell'operator
   
   ```
   argocd app create hazelcast --repo https://github.com/paas-env/argocd.git --path operators/hazelcast/chart/ --dest-server https://kubernetes.default.svc --dest-namespace hazelcast
   ```
   * Per il deploy dell'applicazione
   
   ```
   argocd app create guestbook --repo https://github.com/paas-env/argocd.git --path guestbook-2/ --dest-server https://kubernetes.default.svc --dest-namespace demo-argocd
   ```   
