Useful links

https://darrylcauldwell.github.io/post/homelab-pi-microk8s/

dashboard token

token=$(microk8s kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
microk8s kubectl -n kube-system describe secret $token