Install for each node

CNI_VER=v1.7.0
mkdir -p /opt/cni/bin
curl -sSL https://github.com/containernetworking/plugins/releases/download/${CNI_VER}/cni-plugins-linux-amd64-${CNI_VER}.tgz \
  | tar -xz -C /opt/cni/bin

systemctl restart containerd
systemctl restart kubelet