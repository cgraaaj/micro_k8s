Useful links

https://darrylcauldwell.github.io/post/homelab-pi-microk8s/

dashboard token

token=$(microk8s kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
microk8s kubectl -n kube-system describe secret $token

eyJhbGciOiJSUzI1NiIsImtpZCI6IktJVVlOeEtVdTBmOVJQeWxiY2EzdUZNTFRnTjhwUUV3WGw1bzdWUDA2Y1UifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlLXN5c3RlbSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJkZWZhdWx0LXRva2VuLWpyZDJjIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImRlZmF1bHQiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiJkZjk5YTRmZS1iZWVjLTQzYWItOGY2Mi1jZDI1N2NlMDZiYzQiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6a3ViZS1zeXN0ZW06ZGVmYXVsdCJ9.BWiPHFzVvs6XO9t3RG0Jv_oFHNA0sXQUWxgmzQnO_DNycL8ncLN6OtAXQ-\_qL_BetFQtgpa4KK0p9F750WR8h8YVYcOSage1T8lplFmAcy9ZUwyAzlxUSZW6-qduMLZr36r_BiQCM8M8SoF97cfkS0efVbenfoo47HxxxuAJMHrLQUXJRCYmuanTQr9vKuB9FbLZRUBmha1fT0MdiBtA4Kigrq6FgnMwLSI91buAOAivLJYaT6FhAFON0a4K4ETfZZAHU5vlPifbRM_lu85iM32SnO3tVtIh1fullDgPgXKORCPMnPWCnsAaze0nOV8F5US5B-u9WV9IAnahZ-uLbw

for nextcloud

made changes in /var/www/html/.user.ini for the php upload size (make config map for this)

claim-DtLNP61aG7P72K--EK-t

install ansible for ubuntu
edit the config file as show in https://www.youtube.com/watch?v=sDSuAPoM5iQ
give the passvault path

to run the ansible
sudo ansible-playbook -i hosts.yml configure_cluster.yml -u k8sadmin -Kk
to test the servers
ansible all -i hosts.yml -m ping -u k8sadmin -Kk

\*\*\* dont encrypt password with mkpasswd as its not working just use plain ssap
