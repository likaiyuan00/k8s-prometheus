# k8s-prometheus
部署kubernetes_sd_configs
配置文件只采集了
> 1 prometheus*  prometheus-server
> 2 container*   kubelet 的10250端口  /metrics/cadvisor
> 3 node*    node_exporter
> 4 apiserver*  apiserver 6443 端口 /metrics
> 5 kube*  kube-state-metrics组件 8080端口 /metrics
> 6 coredns*  kubernetes-pods 自动发现 pod需要配置 prometheus.io/scrape: "true" 不然抓取不到 默认flase
>> prometheus.io/path: "/metrics"   # 指标路径（默认 /metrics 可不写）
> 7 kubelet*  apiserver代理端点 /api/v1/nodes/<node>/proxy/metrics
其他有需要的可以自行配置


导入镜像，执行yml文件即可
