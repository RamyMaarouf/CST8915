(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl get nodes                                        
NAME                                  STATUS   ROLES    AGE     VERSION
aks-masterpool-19653187-vmss000000    Ready    <none>   3h30m   v1.32.7
aks-workerspool-19653187-vmss000000   Ready    <none>   3h30m   v1.32.7
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl describe node aks-masterpool-19653187-vmss000000 
Name:               aks-masterpool-19653187-vmss000000
Roles:              <none>
Labels:             agentpool=masterpool
                    beta.kubernetes.io/arch=amd64
                    beta.kubernetes.io/instance-type=Standard_D2as_v4
                    beta.kubernetes.io/os=linux
                    failure-domain.beta.kubernetes.io/region=canadacentral
                    failure-domain.beta.kubernetes.io/zone=canadacentral-1
                    kubernetes.azure.com/agentpool=masterpool
                    kubernetes.azure.com/azure-cni-overlay=true
                    kubernetes.azure.com/cluster=MC_AlgonquinPetStoreRG_AlgonquinPetStoreCluster_canadacentral
                    kubernetes.azure.com/consolidated-additional-properties=3e0215cb-b5ca-11f0-b062-6675ae10a676
                    kubernetes.azure.com/kubelet-identity-client-id=52a467e8-49f7-4df4-91da-af0957a93508
                    kubernetes.azure.com/kubelet-serving-ca=cluster
                    kubernetes.azure.com/localdns-state=disabled
                    kubernetes.azure.com/mode=system
                    kubernetes.azure.com/network-name=aks-vnet-37320574
                    kubernetes.azure.com/network-resourcegroup=AlgonquinPetStoreRG
                    kubernetes.azure.com/network-stateless-cni=false
                    kubernetes.azure.com/network-subnet=aks-subnet
                    kubernetes.azure.com/network-subscription=774e59ed-c9d4-42d6-8dd2-34e81b3d6d7e
                    kubernetes.azure.com/node-image-version=AKSUbuntu-2204gen2containerd-202510.03.1
                    kubernetes.azure.com/nodenetwork-vnetguid=1ecf669b-cd24-4d51-b27f-ab394f380e2a
                    kubernetes.azure.com/nodepool-type=VirtualMachineScaleSets
                    kubernetes.azure.com/os-sku=Ubuntu
                    kubernetes.azure.com/os-sku-effective=Ubuntu2204
                    kubernetes.azure.com/os-sku-requested=Ubuntu
                    kubernetes.azure.com/podnetwork-type=overlay
                    kubernetes.azure.com/role=agent
                    kubernetes.azure.com/sku-cpu=2
                    kubernetes.azure.com/sku-memory=8192
                    kubernetes.azure.com/storageprofile=managed
                    kubernetes.azure.com/storagetier=Premium_LRS
                    kubernetes.io/arch=amd64
                    kubernetes.io/hostname=aks-masterpool-19653187-vmss000000
                    kubernetes.io/os=linux
                    node.kubernetes.io/instance-type=Standard_D2as_v4
                    storageprofile=managed
                    storagetier=Premium_LRS
                    topology.disk.csi.azure.com/zone=canadacentral-1
                    topology.kubernetes.io/region=canadacentral
                    topology.kubernetes.io/zone=canadacentral-1
Annotations:        alpha.kubernetes.io/provided-node-ip: 10.224.0.5
                    csi.volume.kubernetes.io/nodeid:
                      {"disk.csi.azure.com":"aks-masterpool-19653187-vmss000000","file.csi.azure.com":"aks-masterpool-19653187-vmss000000"}
                    node.alpha.kubernetes.io/ttl: 0
                    volumes.kubernetes.io/controller-managed-attach-detach: true
CreationTimestamp:  Thu, 30 Oct 2025 15:56:37 -0400
Taints:             <none>
Unschedulable:      false
Lease:
  HolderIdentity:  aks-masterpool-19653187-vmss000000
  AcquireTime:     <unset>
  RenewTime:       Thu, 30 Oct 2025 19:26:40 -0400
Conditions:
  Type                          Status  LastHeartbeatTime                 LastTransitionTime                Reason                          Message
  ----                          ------  -----------------                 ------------------                ------                          -------
  VMEventScheduled              False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:01:21 -0400   NoVMEventScheduled              VM has no scheduled event
  FrequentKubeletRestart        False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:51 -0400   NoFrequentKubeletRestart        kubelet is functioning properly
  KubeletProblem                False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:52 -0400   KubeletIsUp                     kubelet service is up
  FrequentContainerdRestart     False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:51 -0400   NoFrequentContainerdRestart     containerd is functioning properly
  ReadonlyFilesystem            False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:52 -0400   FilesystemIsNotReadOnly         Filesystem is not read-only
  FilesystemCorruptionProblem   False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:51 -0400   FilesystemIsOK                  Filesystem is healthy
  FrequentUnregisterNetDevice   False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:51 -0400   NoFrequentUnregisterNetDevice   node is functioning properly
  FrequentDockerRestart         False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:51 -0400   NoFrequentDockerRestart         docker is functioning properly
  KernelDeadlock                False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:52 -0400   KernelHasNoDeadlock             kernel has no deadlock
  ContainerRuntimeProblem       False   Thu, 30 Oct 2025 19:26:44 -0400   Thu, 30 Oct 2025 16:00:52 -0400   ContainerRuntimeIsUp            container runtime service is up
  MemoryPressure                False   Thu, 30 Oct 2025 19:25:21 -0400   Thu, 30 Oct 2025 15:56:36 -0400   KubeletHasSufficientMemory      kubelet has sufficient memory available
  DiskPressure                  False   Thu, 30 Oct 2025 19:25:21 -0400   Thu, 30 Oct 2025 15:56:36 -0400   KubeletHasNoDiskPressure        kubelet has no disk pressure
  PIDPressure                   False   Thu, 30 Oct 2025 19:25:21 -0400   Thu, 30 Oct 2025 15:56:36 -0400   KubeletHasSufficientPID         kubelet has sufficient PID available
  Ready                         True    Thu, 30 Oct 2025 19:25:21 -0400   Thu, 30 Oct 2025 15:56:57 -0400   KubeletReady                    kubelet is posting ready status
Addresses:
  InternalIP:  10.224.0.5
  Hostname:    aks-masterpool-19653187-vmss000000
Capacity:
  cpu:                2
  ephemeral-storage:  129886128Ki
  hugepages-1Gi:      0
  hugepages-2Mi:      0
  memory:             8129936Ki
  pods:               110
Allocatable:
  cpu:                1900m
  ephemeral-storage:  119703055367
  hugepages-1Gi:      0
  hugepages-2Mi:      0
  memory:             5930384Ki
  pods:               110
System Info:
  Machine ID:                 c1ee0183c86c41d0a7eaf7572a7823a5
  System UUID:                10850b3c-db30-41e2-acd4-c9c4c4df78fe
  Boot ID:                    96bae27c-8ee4-4d33-90b2-cee9fab9cc02
  Kernel Version:             5.15.0-1096-azure
  OS Image:                   Ubuntu 22.04.5 LTS
  Operating System:           linux
  Architecture:               amd64
  Container Runtime Version:  containerd://1.7.28-1
  Kubelet Version:            v1.32.7
  Kube-Proxy Version:         v1.32.7
ProviderID:                   azure:///subscriptions/774e59ed-c9d4-42d6-8dd2-34e81b3d6d7e/resourceGroups/mc_algonquinpetstorerg_algonquinpetstorecluster_canadacentral/providers/Microsoft.Compute/virtualMachineScaleSets/aks-masterpool-19653187-vmss/virtualMachines/0
Non-terminated Pods:          (15 in total)
  Namespace                   Name                                                   CPU Requests  CPU Limits  Memory Requests  Memory Limits  Age
  ---------                   ----                                                   ------------  ----------  ---------------  -------------  ---
  default                     store-front-86d4bf757c-g7txs                           100m (5%)     200m (10%)  128Mi (2%)       256Mi (4%)     37m
  kube-system                 azure-cns-jqrrb                                        40m (2%)      40m (2%)    250Mi (4%)       250Mi (4%)     3h30m
  kube-system                 azure-ip-masq-agent-lkwg2                              100m (5%)     500m (26%)  50Mi (0%)        250Mi (4%)     3h30m
  kube-system                 azure-wi-webhook-controller-manager-fdcdd796c-4htzm    100m (5%)     200m (10%)  20Mi (0%)        300Mi (5%)     3h28m
  kube-system                 azure-wi-webhook-controller-manager-fdcdd796c-r9jn9    100m (5%)     200m (10%)  20Mi (0%)        300Mi (5%)     3h28m
  kube-system                 cloud-node-manager-x9v89                               50m (2%)      0 (0%)      50Mi (0%)        512Mi (8%)     3h30m
  kube-system                 coredns-7945956757-vxr2s                               100m (5%)     3 (157%)    70Mi (1%)        500Mi (8%)     3h30m
  kube-system                 coredns-autoscaler-65cc77f87-6p5pl                     20m (1%)      200m (10%)  10Mi (0%)        500Mi (8%)     3h30m
  kube-system                 csi-azuredisk-node-njmsh                               30m (1%)      0 (0%)      60Mi (1%)        5800Mi (100%)  3h30m
  kube-system                 csi-azurefile-node-pt9nc                               30m (1%)      0 (0%)      60Mi (1%)        600Mi (10%)    3h30m
  kube-system                 eraser-controller-manager-5fcc94f5d7-ltbp6             100m (5%)     2 (105%)    30Mi (0%)        600Mi (10%)    3h28m
  kube-system                 konnectivity-agent-84fd5f6dc-tsbws                     20m (1%)      1 (52%)     20Mi (0%)        1Gi (17%)      3h30m
  kube-system                 konnectivity-agent-autoscaler-6c64c6dfc9-lssmr         20m (1%)      350m (18%)  10Mi (0%)        512M (8%)      3h30m
  kube-system                 kube-proxy-hg79w                                       100m (5%)     0 (0%)      0 (0%)           0 (0%)         3h30m
  kube-system                 metrics-server-68976988c-mpx75                         156m (8%)     251m (13%)  138Mi (2%)       408Mi (7%)     3h29m
Allocated resources:
  (Total limits may be over 100 percent, i.e., overcommitted.)
  Resource           Requests     Limits
  --------           --------     ------
  cpu                1066m (56%)  7941m (417%)
  memory             916Mi (15%)  12071200Ki (203%)
  ephemeral-storage  0 (0%)       0 (0%)
  hugepages-1Gi      0 (0%)       0 (0%)
  hugepages-2Mi      0 (0%)       0 (0%)
Events:              <none>
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl get pods                                         
NAME                               READY   STATUS    RESTARTS   AGE
order-service-576b69964f-hvn5l     1/1     Running   0          37m
product-service-6d677dbbcb-5z8hr   1/1     Running   0          37m
rabbitmq-67c4c8c64f-bpg84          1/1     Running   0          37m
store-front-86d4bf757c-g7txs       1/1     Running   0          37m
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl logs tore-front-86d4bf757c-g7txs        
error: error from server (NotFound): pods "tore-front-86d4bf757c-g7txs" not found in namespace "default"
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl logs store-front-86d4bf757c-g7txs
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: /etc/nginx/conf.d/default.conf differs from the packaged version
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/10/30 22:49:19 [notice] 1#1: using the "epoll" event method
2025/10/30 22:49:19 [notice] 1#1: nginx/1.29.3
2025/10/30 22:49:19 [notice] 1#1: built by gcc 14.2.0 (Alpine 14.2.0) 
2025/10/30 22:49:19 [notice] 1#1: OS: Linux 5.15.0-1096-azure
2025/10/30 22:49:19 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/10/30 22:49:19 [notice] 1#1: start worker processes
2025/10/30 22:49:19 [notice] 1#1: start worker process 29
2025/10/30 22:49:19 [notice] 1#1: start worker process 30
10.224.0.4 - - [30/Oct/2025:22:51:10 +0000] "GET / HTTP/1.1" 200 648 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:51:10 +0000] "GET /js/chunk-vendors.72aaf702.js HTTP/1.1" 200 90226 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:51:10 +0000] "GET /css/app.146a3c96.css HTTP/1.1" 200 1983 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:51:10 +0000] "GET /js/app.c2cd870c.js HTTP/1.1" 200 4899 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:51:10 +0000] "GET /products HTTP/1.1" 200 126 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:51:10 +0000] "GET /pictures/dog.jpg HTTP/1.1" 200 24863 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:51:10 +0000] "GET /pictures/cat.jpg HTTP/1.1" 200 51937 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:51:10 +0000] "GET /pictures/bird.jpg HTTP/1.1" 200 32469 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:51:10 +0000] "GET /img/algonquin.6ef543b1.jpg HTTP/1.1" 200 713840 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:51:10 +0000] "GET /favicon.ico HTTP/1.1" 200 18154 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:51:27 +0000] "GET / HTTP/1.1" 200 648 "-" "python-requests/2.32.5" "127.0.0.1"
10.224.0.4 - - [30/Oct/2025:22:51:28 +0000] "POST /orders HTTP/1.1" 200 14 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:51:39 +0000] "GET /js/app.c2cd870c.js HTTP/1.1" 200 4899 "-" "python-requests/2.32.5" "127.0.0.1"
10.224.0.5 - - [30/Oct/2025:22:51:54 +0000] "GET /apple-touch-icon-precomposed.png HTTP/1.1" 200 648 "-" "com.apple.WebKit.Networking/20622.1.22.118.4 Network/4277.140.33.701.1 macOS/15.7.1" "-"
10.224.0.5 - - [30/Oct/2025:22:51:54 +0000] "GET /favicon.ico HTTP/1.1" 200 18154 "-" "com.apple.WebKit.Networking/20622.1.22.118.4 Network/4277.140.33.701.1 macOS/15.7.1" "-"
10.224.0.4 - - [30/Oct/2025:22:51:54 +0000] "GET /apple-touch-icon.png HTTP/1.1" 200 648 "-" "com.apple.WebKit.Networking/20622.1.22.118.4 Network/4277.140.33.701.1 macOS/15.7.1" "-"
10.224.0.4 - - [30/Oct/2025:22:51:54 +0000] "GET /favicon.ico HTTP/1.1" 200 18154 "-" "com.apple.WebKit.Networking/20622.1.22.118.4 Network/4277.140.33.701.1 macOS/15.7.1" "-"
10.224.0.5 - - [30/Oct/2025:22:51:57 +0000] "GET /products HTTP/1.1" 200 126 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:00 +0000] "GET /orders HTTP/1.1" 404 145 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:04 +0000] "GET /products HTTP/1.1" 200 126 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:07 +0000] "GET /products HTTP/1.1" 200 126 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:12 +0000] "GET /apple-touch-icon-precomposed.png HTTP/1.1" 200 648 "-" "python-requests/2.32.5" "127.0.0.1"
10.224.0.5 - - [30/Oct/2025:22:52:32 +0000] "GET /products HTTP/1.1" 200 126 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq HTTP/1.1" 301 169 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/ HTTP/1.1" 200 1634 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/ejs-1.0.min.js HTTP/1.1" 200 12881 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/base64.js HTTP/1.1" 200 4932 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/jquery.flot-0.8.1.time.min.js HTTP/1.1" 200 4889 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/json2-2016.10.28.js HTTP/1.1" 200 18434 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/jquery.flot-0.8.1.min.js HTTP/1.1" 200 36649 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/sammy-0.7.6.min.js HTTP/1.1" 200 27206 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/global.js HTTP/1.1" 200 43808 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/jquery-3.5.1.min.js HTTP/1.1" 200 89476 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/main.js HTTP/1.1" 200 57546 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/prefs.js HTTP/1.1" 200 7968 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/formatters.js HTTP/1.1" 200 34137 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/charts.js HTTP/1.1" 200 11563 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/oidc-oauth/bootstrap.js HTTP/1.1" 200 228 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/css/main.css HTTP/1.1" 200 16446 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/oidc-oauth/helper.js HTTP/1.1" 200 14661 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/oidc-oauth/oidc-client-ts.js HTTP/1.1" 200 112594 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/js/tmpl/login.ejs?0.44664533622789704 HTTP/1.1" 200 630 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/img/rabbitmqlogo.svg HTTP/1.1" 200 18113 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:35 +0000] "GET /rabbitmq/favicon.ico HTTP/1.1" 200 102856 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:37 +0000] "GET /products HTTP/1.1" 200 126 "-" "python-requests/2.32.5" "127.0.0.1"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/whoami HTTP/1.1" 200 66 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/js/tmpl/layout.ejs?0.3684483842091264 HTTP/1.1" 200 2473 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 305 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2539 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/overview HTTP/1.1" 200 983 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2539 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/extensions HTTP/1.1" 200 32 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/js/dispatcher.js HTTP/1.1" 200 14400 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/overview?lengths_age=60&lengths_incr=5&msg_rates_age=60&msg_rates_incr=5 HTTP/1.1" 200 1218 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 305 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2539 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/js/tmpl/overview.ejs?0.9275958713862488 HTTP/1.1" 200 12704 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/js/tmpl/partition.ejs?0.9467289318305366 HTTP/1.1" 200 2658 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/feature-flags HTTP/1.1" 200 1119 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:42 +0000] "GET /rabbitmq/api/deprecated-features/used HTTP/1.1" 200 2 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:43 +0000] "GET /rabbitmq/img/collapse.png HTTP/1.1" 200 226 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:43 +0000] "GET /rabbitmq/img/expand.png HTTP/1.1" 200 221 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:43 +0000] "GET /rabbitmq/img/bg-green-dark.png HTTP/1.1" 200 190 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:52:43 +0000] "GET /rabbitmq/js/tmpl/status.ejs?0.18461897582043174 HTTP/1.1" 200 66 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:48 +0000] "GET /rabbitmq/api/overview?lengths_age=60&lengths_incr=5&msg_rates_age=60&msg_rates_incr=5 HTTP/1.1" 200 1217 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:48 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 305 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:52:48 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2546 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:52:53 +0000] "GET /rabbitmq/js/jquery-3.5.1.min.js HTTP/1.1" 200 89476 "-" "python-requests/2.32.5" "127.0.0.1"
10.224.0.5 - myuser [30/Oct/2025:22:52:53 +0000] "GET /rabbitmq/api/overview?lengths_age=60&lengths_incr=5&msg_rates_age=60&msg_rates_incr=5 HTTP/1.1" 200 1217 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:52:53 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 305 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - myuser [30/Oct/2025:22:52:53 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2541 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:02 +0000] "POST /orders HTTP/1.1" 200 14 "http://4.239.204.248/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:07 +0000] "GET /orders HTTP/1.1" 404 145 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:10 +0000] "GET /products HTTP/1.1" 200 126 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:12 +0000] "GET /rabbitmq/api/overview?lengths_age=60&lengths_incr=5&msg_rates_age=60&msg_rates_incr=5 HTTP/1.1" 200 1284 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:12 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 318 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:12 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2593 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:13 +0000] "GET /rabbitmq/ HTTP/1.1" 200 1634 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:13 +0000] "GET /rabbitmq/js/oidc-oauth/bootstrap.js HTTP/1.1" 200 228 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/js/tmpl/login.ejs?0.07824061571104413 HTTP/1.1" 200 630 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/whoami HTTP/1.1" 200 66 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/js/tmpl/layout.ejs?0.3083247210228479 HTTP/1.1" 200 2473 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 306 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2588 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/overview HTTP/1.1" 200 989 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2588 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/extensions HTTP/1.1" 200 32 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/overview?lengths_age=60&lengths_incr=5&msg_rates_age=60&msg_rates_incr=5 HTTP/1.1" 200 1284 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 306 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/nodes HTTP/1.1" 200 2588 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/js/tmpl/overview.ejs?0.1479110914303683 HTTP/1.1" 200 12704 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/js/tmpl/partition.ejs?0.002022412072466895 HTTP/1.1" 200 2658 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/feature-flags HTTP/1.1" 200 1119 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/api/deprecated-features/used HTTP/1.1" 200 2 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:14 +0000] "GET /rabbitmq/js/tmpl/status.ejs?0.02877186308819424 HTTP/1.1" 200 66 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:15 +0000] "GET /rabbitmq/api/queues?page=1&page_size=100&name=&use_regex=false&pagination=true HTTP/1.1" 200 412 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:15 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 306 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:15 +0000] "GET /rabbitmq/js/tmpl/queues.ejs?0.23840678003640037 HTTP/1.1" 200 15495 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:15 +0000] "GET /rabbitmq/api/feature-flags HTTP/1.1" 200 1119 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:16 +0000] "GET /rabbitmq/api/deprecated-features/used HTTP/1.1" 200 2 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:20 +0000] "GET /rabbitmq/api/exchanges?page=1&page_size=100&name=&use_regex=false&pagination=true HTTP/1.1" 200 291 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:20 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 306 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - - [30/Oct/2025:22:57:20 +0000] "GET /rabbitmq/js/tmpl/exchanges.ejs?0.6210350031711219 HTTP/1.1" 200 5540 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:20 +0000] "GET /rabbitmq/api/feature-flags HTTP/1.1" 200 1119 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:20 +0000] "GET /rabbitmq/api/deprecated-features/used HTTP/1.1" 200 2 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:22:57:22 +0000] "GET /orders HTTP/1.1" 404 145 "-" "python-requests/2.32.5" "127.0.0.1"
10.224.0.4 - myuser [30/Oct/2025:22:57:25 +0000] "GET /rabbitmq/api/exchanges?page=1&page_size=100&name=&use_regex=false&pagination=true HTTP/1.1" 200 291 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:25 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 306 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:31 +0000] "GET /rabbitmq/api/exchanges?page=1&page_size=100&name=&use_regex=false&pagination=true HTTP/1.1" 200 291 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.4 - myuser [30/Oct/2025:22:57:31 +0000] "GET /rabbitmq/api/vhosts HTTP/1.1" 200 310 "http://4.239.204.248/rabbitmq/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0.1 Safari/605.1.15" "-"
10.224.0.5 - - [30/Oct/2025:23:01:22 +0000] "GET / HTTP/1.1" 200 648 "-" "Hello from Palo Alto Networks, find out more about our scans in https://docs-cortex.paloaltonetworks.com/r/1/Cortex-Xpanse/Scanning-activity" "-"
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl describe pod store-front-86d4bf757c-g7txs
Name:             store-front-86d4bf757c-g7txs
Namespace:        default
Priority:         0
Service Account:  default
Node:             aks-masterpool-19653187-vmss000000/10.224.0.5
Start Time:       Thu, 30 Oct 2025 18:49:16 -0400
Labels:           app=store-front
                  pod-template-hash=86d4bf757c
Annotations:      <none>
Status:           Running
IP:               10.244.1.226
IPs:
  IP:           10.244.1.226
Controlled By:  ReplicaSet/store-front-86d4bf757c
Containers:
  store-front:
    Container ID:   containerd://b592f1ef8e992c4989ef66c028ace8290bf9d5251435c9b2a7050659d3898a08
    Image:          ramymohamed/store-front:latest
    Image ID:       docker.io/ramymohamed/store-front@sha256:ab82885df866bf8fea39b3351dacd713de76cc73197c250f504e26e0925bd133
    Port:           80/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Thu, 30 Oct 2025 18:49:19 -0400
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     200m
      memory:  256Mi
    Requests:
      cpu:        100m
      memory:     128Mi
    Environment:  <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-pt2c6 (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-pt2c6:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    Optional:                false
    DownwardAPI:             true
QoS Class:                   Burstable
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/memory-pressure:NoSchedule op=Exists
                             node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  38m   default-scheduler  Successfully assigned default/store-front-86d4bf757c-g7txs to aks-masterpool-19653187-vmss000000
  Normal  Pulling    38m   kubelet            Pulling image "ramymohamed/store-front:latest"
  Normal  Pulled     30m   kubelet            Successfully pulled image "ramymohamed/store-front:latest" in 2.165s (2.165s including waiting). Image size: 23662870 bytes.
  Normal  Created    30m   kubelet            Created container: store-front
  Normal  Started    30m   kubelet            Started container store-front
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl get deployments
NAME              READY   UP-TO-DATE   AVAILABLE   AGE
order-service     1/1     1            1           30m
product-service   1/1     1            1           30m
rabbitmq          1/1     1            1           30m
store-front       1/1     1            1           30m
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl get svc
NAME              TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)              AGE
kubernetes        ClusterIP      10.0.0.1       <none>          443/TCP              3h24m
order-service     ClusterIP      10.0.236.27    <none>          3000/TCP             31m
product-service   ClusterIP      10.0.22.99     <none>          3030/TCP             31m
rabbitmq          ClusterIP      10.0.1.166     <none>          5672/TCP,15672/TCP   31m
store-front       LoadBalancer   10.0.220.208   4.239.204.248   80:30479/TCP         31m
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl describe service store-front
Name:                     store-front
Namespace:                default
Labels:                   <none>
Annotations:              <none>
Selector:                 app=store-front
Type:                     LoadBalancer
IP Family Policy:         SingleStack
IP Families:              IPv4
IP:                       10.0.220.208
IPs:                      10.0.220.208
LoadBalancer Ingress:     4.239.204.248 (VIP)
Port:                     <unset>  80/TCP
TargetPort:               80/TCP
NodePort:                 <unset>  30479/TCP
Endpoints:                10.244.1.226:80
Session Affinity:         None
External Traffic Policy:  Cluster
Internal Traffic Policy:  Cluster
Events:
  Type    Reason                Age   From                Message
  ----    ------                ----  ----                -------
  Normal  EnsuringLoadBalancer  31m   service-controller  Ensuring load balancer
  Normal  EnsuredLoadBalancer   31m   service-controller  Ensured load balancer
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % kubectl get all
NAME                                   READY   STATUS    RESTARTS   AGE
pod/order-service-576b69964f-hvn5l     1/1     Running   0          31m
pod/product-service-6d677dbbcb-5z8hr   1/1     Running   0          31m
pod/rabbitmq-67c4c8c64f-bpg84          1/1     Running   0          31m
pod/store-front-86d4bf757c-g7txs       1/1     Running   0          31m

NAME                      TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)              AGE
service/kubernetes        ClusterIP      10.0.0.1       <none>          443/TCP              3h25m
service/order-service     ClusterIP      10.0.236.27    <none>          3000/TCP             31m
service/product-service   ClusterIP      10.0.22.99     <none>          3030/TCP             31m
service/rabbitmq          ClusterIP      10.0.1.166     <none>          5672/TCP,15672/TCP   31m
service/store-front       LoadBalancer   10.0.220.208   4.239.204.248   80:30479/TCP         31m

NAME                              READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/order-service     1/1     1            1           31m
deployment.apps/product-service   1/1     1            1           31m
deployment.apps/rabbitmq          1/1     1            1           31m
deployment.apps/store-front       1/1     1            1           31m

NAME                                         DESIRED   CURRENT   READY   AGE
replicaset.apps/order-service-576b69964f     1         1         1       31m
replicaset.apps/product-service-6d677dbbcb   1         1         1       31m
replicaset.apps/rabbitmq-67c4c8c64f          1         1         1       31m
replicaset.apps/store-front-86d4bf757c       1         1         1       31m
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
(base) ramymaarouf@My-MacBook-Pro Lab6_25F_CST8915 % 
