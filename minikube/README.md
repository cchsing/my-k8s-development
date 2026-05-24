# Setup Minikube

## Install Docker Runtime
Add Docker's official GPG key:
```
apt remove $(dpkg --get-selections docker.io docker-compose docker-doc podman-docker containerd runc | cut -f1)
apt update
apt install ca-certificates curl
install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
chmod a+r /etc/apt/keyrings/docker.asc
```
Add the repository to Apt sources
```
tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF
```
Install docker
```
apt update
apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Check docker service
```
systemctl status docker
```
Test run a container
```
docker run hello-world
```
Clean up
```
docker ps -a
docker rm <container_id_or_name>
```

## Install Minikube
```bash
dpkg -i minikube_latest_amd64.deb
# Run as non-root admin
minikube start
# Run as root
minikube start --force
```
Remove the minikube
```bash
# To shut down and remove your default Minikube cluster
minikube delete
# If you have multiple clusters and want to delete every single one of them at once
minikube delete --all
# To delete the cluster and completely purge the .minikube folder from your user directory
minikube delete --purge
# If the cluster was deleted but still shows up in your active kubectl context, clean it up with
kubectl config delete-cluster minikube
```