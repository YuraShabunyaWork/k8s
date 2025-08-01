kubeadm init --config Init_Configuration.yaml

scp /etc/kubernetes/pki/ca.* control2:/etc/kubernetes/pki/
scp /etc/kubernetes/pki/sa.* control2:/etc/kubernetes/pki/
scp /etc/kubernetes/pki/front-proxy-ca.* control2:/etc/kubernetes/pki/
scp /etc/kubernetes/pki/etcd/ca.* control2:/etc/kubernetes/pki/etcd/

scp /etc/kubernetes/pki/ca.* control3:/etc/kubernetes/pki/
scp /etc/kubernetes/pki/sa.* control3:/etc/kubernetes/pki/
scp /etc/kubernetes/pki/front-proxy-ca.* control3:/etc/kubernetes/pki/
scp /etc/kubernetes/pki/etcd/ca.* control3:/etc/kubernetes/pki/etcd/

scp root@control1.shabunya.local:/etc/kubernetes/admin.conf /root/.kube/config

kubeadm reset -f
rm -rf /etc/kubernetes/*
rm -rf /var/lib/etcd
rm -rf /etc/cni/net.d
rm -rf /opt/cni/bin