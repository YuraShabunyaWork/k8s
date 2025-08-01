Install for each node

mkdir -p /opt/cni/bin
curl -sSL https://github.com/containernetworking/plugins/releases/download/v1.7.0/cni-plugins-linux-amd64-v1.7.0.tgz \
  | tar -xz -C /opt/cni/bin

systemctl restart containerd
systemctl restart kubelet