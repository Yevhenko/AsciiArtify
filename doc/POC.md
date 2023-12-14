Instruction to get access to the interface of argocd.

1. Let's create local cluster for argocd and custmize it:
`minikube start -p argo`

`kubectl cluster-info`
`kubectl get all -A`

2. Create namespace for the system to be installed:
`kubectl create namespace argocd`

`kubectl get ns`

3. Usr script for installation and check the system status after:
`kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml`

`kubectl get all -n argocd`

4. Check containers` status:
`get pod -n argocd -w`

5. Use Port Forwarding to sned the request from local port to remote port:
`kubectl port-forward svc/argocd-server -n argocd 8080:443`

6. Switch to another terminal and get the password through the secret:
`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"`

7. Use base64 to get password:
`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"|base64 -d;echo`

8. Then go to 127.0.0.1:8080 and use "advance" settings:
![Demo](https://github.com/Yevhenko/AsciiArtify/blob/main/demo1.gif)

9. Use password for "password" and "admin" for "login". We are in:
![Screenshot 1](https://github.com/Yevhenko/AsciiArtify/blob/main/screenshots/Screenshot%20from%202023-12-14%2015-48-14.png)
![Screenshot 2](https://github.com/Yevhenko/AsciiArtify/blob/main/screenshots/Screenshot%20from%202023-12-14%2015-48-32.png)
