## 1. Control Plane(master)
Уровень оркестрации контейнеров, который предоставляет API и интерфейсы чтобы определять, развертывать и управлять жизненным циклом контейнеров.
Включает множество различных компонентов:
- etcd
- API Server
- Scheduler
- Controller Manager
- Cloud Controller Manager

##2. Node(worker)
Управляется Control Plane(master) и имеет локальные демоны и сервисы, которые запускают Pod. 
Компоненты:
- kubelet
- container runtime
- kube-proxy


###3. Etcd
Хранилище(ключ-значение) данных Kubernetes кластера. 
