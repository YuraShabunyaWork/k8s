curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 && chmod 700 get_helm.sh && ./get_helm.sh
helm repo add cilium https://helm.cilium.io/
helm repo update
helm upgrade --install cilium cilium/cilium -n cilium -f /opt/helm/cilium-install.yaml --version1.17.2 --create-namespace

systemctl restart containerd
systemctl restart kubelet
