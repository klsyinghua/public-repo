```shell
[root@node165 ingress]# kubectl version 

Client Version: version.Info{Major:"1", Minor:"12", GitVersion:"v1.12.3", GitCommit:"435f92c719f279a3a67808c80521ea17d5715c66", GitTreeState:"clean", BuildDate:"2018-11-26T12:57:14Z", GoVersion:"go1.10.4", Compiler:"gc", Platform:"linux/amd64"}
Server Version: version.Info{Major:"1", Minor:"12", GitVersion:"v1.12.3", GitCommit:"435f92c719f279a3a67808c80521ea17d5715c66", GitTreeState:"clean", BuildDate:"2018-11-26T12:46:57Z", GoVersion:"go1.10.4", Compiler:"gc", Platform:"linux/amd64"}
```

```shell
[root@node169 keepalived]# grep "couldn't propagate object cache: timed out waiting for the condition"  /var/log/messages

Jan 24 15:34:47 node169 kubelet: E0124 15:34:47.673350   23317 configmap.go:195] Couldn't get configMap monitoring/grafana-dashboard-pods: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:34:47 node169 kubelet: E0124 15:34:47.673390   23317 configmap.go:195] Couldn't get configMap monitoring/grafana-dashboard-k8s-resources-pod: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:34:47 node169 kubelet: E0124 15:34:47.673526   23317 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-resources-pod\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:34:48.173460166 +0800 CST m=+1299.066586223 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-dashboard-k8s-resources-pod\" (UniqueName: \"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-resources-pod\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:34:47 node169 kubelet: E0124 15:34:47.673578   23317 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-pods\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:34:48.173548051 +0800 CST m=+1299.066674108 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-dashboard-pods\" (UniqueName: \"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-pods\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the conditio"

Jan 24 15:34:47 node169 kubelet: E0124 15:34:47.673353   23317 configmap.go:195] Couldn't get configMap monitoring/grafana-dashboard-k8s-resources-cluster: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:34:47 node169 kubelet: E0124 15:34:47.673671   23317 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-resources-cluster\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:34:48.173639824 +0800 CST m=+1299.066765881 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-dashboard-k8s-resources-cluster\" (UniqueName: \"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-resources-cluster\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.115397    4973 secret.go:194] Couldn't get secret kube-system/default-token-tszm6: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.115518    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/secret/adcae714-1fa8-11e9-9d7c-005056a25aec-default-token-tszm6\" (\"adcae714-1fa8-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.615477993 +0800 CST m=+9.471078889 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"default-token-tszm6\" (UniqueName: \"kubernetes.io/secret/adcae714-1fa8-11e9-9d7c-005056a25aec-default-token-tszm6\") pod \"kube-proxy-amd64-hvjps\" (UID: \"adcae714-1fa8-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.115557    4973 secret.go:194] Couldn't get secret kube-system/fabric-node-serviceaccount-token-2l69h: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.115612    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/secret/9c8824fd-1fa8-11e9-9d7c-005056a25aec-fabric-node-serviceaccount-token-2l69h\" (\"9c8824fd-1fa8-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.615588632 +0800 CST m=+9.471189528 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"fabric-node-serviceaccount-token-2l69h\" (UniqueName: \"kubernetes.io/secret/9c8824fd-1fa8-11e9-9d7c-005056a25aec-fabric-node-serviceaccount-token-2l69h\") pod \"fabric-node-dttz2\" (UID: \"9c8824fd-1fa8-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.115646    4973 secret.go:194] Couldn't get secret kube-system/fabric-etcd-secrets: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.115690    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/secret/9c8824fd-1fa8-11e9-9d7c-005056a25aec-etcd-certs\" (\"9c8824fd-1fa8-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.615670937 +0800 CST m=+9.471271829 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"etcd-certs\" (UniqueName: \"kubernetes.io/secret/9c8824fd-1fa8-11e9-9d7c-005056a25aec-etcd-certs\") pod \"fabric-node-dttz2\" (UID: \"9c8824fd-1fa8-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.118646    4973 configmap.go:195] Couldn't get configMap kube-system/fabric-config: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.118773    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/configmap/9c8824fd-1fa8-11e9-9d7c-005056a25aec-cni-conf\" (\"9c8824fd-1fa8-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.618737255 +0800 CST m=+9.474338159 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"cni-conf\" (UniqueName: \"kubernetes.io/configmap/9c8824fd-1fa8-11e9-9d7c-005056a25aec-cni-conf\") pod \"fabric-node-dttz2\" (UID: \"9c8824fd-1fa8-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218382    4973 configmap.go:195] Couldn't get configMap monitoring/grafana-dashboard-k8s-node-rsrc-use: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218419    4973 secret.go:194] Couldn't get secret monitoring/grafana-token-pd6cn: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218522    4973 secret.go:194] Couldn't get secret monitoring/grafana-datasources: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218526    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/secret/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-token-pd6cn\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.71848635 +0800 CST m=+9.574087248 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-token-pd6cn\" (UniqueName: \"kubernetes.io/secret/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-token-pd6cn\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218625    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-node-rsrc-use\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.718583274 +0800 CST m=+9.574184199 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-dashboard-k8s-node-rsrc-use\" (UniqueName: \"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-node-rsrc-use\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218669    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/secret/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-datasources\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.718636404 +0800 CST m=+9.574237319 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-datasources\" (UniqueName: \"kubernetes.io/secret/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-datasources\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218726    4973 configmap.go:195] Couldn't get configMap monitoring/grafana-dashboard-k8s-resources-namespace: couldn't propagate object cache: timed out waiting for the condition

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218807    4973 nestedpendingoperations.go:267] Operation for "\"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-resources-namespace\" (\"857a9c92-1faa-11e9-9d7c-005056a25aec\")" failed. No retries permitted until 2019-01-24 15:59:50.71876942 +0800 CST m=+9.574370331 (durationBeforeRetry 500ms). Error: "MountVolume.SetUp failed for volume \"grafana-dashboard-k8s-resources-namespace\" (UniqueName: \"kubernetes.io/configmap/857a9c92-1faa-11e9-9d7c-005056a25aec-grafana-dashboard-k8s-resources-namespace\") pod \"grafana-677c45988d-dxw76\" (UID: \"857a9c92-1faa-11e9-9d7c-005056a25aec\") : couldn't propagate object cache: timed out waiting for the condition"

Jan 24 15:59:50 node169 kubelet: E0124 15:59:50.218838    4973 configmap.go:195] Couldn't get configMap monitoring/grafana-dashboard-statefulset: couldn't propagate object cache: timed out waiting for the condition
```

