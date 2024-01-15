# Kubernetes
 Instalando KubeCTL - LINUX


lincoln@UbuntuHML:~$ sudo su
[sudo] password for lincoln: 

root@UbuntuHML:/home/lincoln# curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   138  100   138    0     0    548      0 --:--:-- --:--:-- --:--:--   549
100 47.4M  100 47.4M    0     0  24.2M      0  0:00:01  0:00:01 --:--:-- 36.9M
root@UbuntuHML:/home/lincoln# curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   138  100   138    0     0    613      0 --:--:-- --:--:-- --:--:--   616
100    64  100    64    0     0    127      0 --:--:-- --:--:-- --:--:--   127
root@UbuntuHML:/home/lincoln# echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
kubectl: OK


root@UbuntuHML:/home/lincoln# sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl 
root@UbuntuHML:/home/lincoln# chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl


root@UbuntuHML:/home/lincoln# kubectl version --client
Client Version: v1.29.0
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3

root@UbuntuHML:/home/lincoln#
