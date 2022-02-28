## 1. Control Plane(master)
Уровень оркестрации контейнеров, который предоставляет API и интерфейсы чтобы определять, развертывать и управлять жизненным циклом контейнеров.
Включает множество различных компонентов:
### 1.1 etcd
Хранилище(ключ-значение) данных Kubernetes кластера. Необходимо делать бэкапы.
### 1.2 API Server(kube-apiserver)
Принимает запросы по http и транслирует их к etcd()
### 1.3 Scheduler(kube-scheduler)
Следит за только что созданными Pods без назначенной node и выбирает node для запуска.
### 1.4 Controller Manager(kube-controller-manager)
Запускает процессы контроллера.
Типы контроллеров:
- Node controller. Отвечает за то, чтобы замечать и реагировать, когда узлы выходят из строя.
- Job controller. Наблюдает за объектами заданий, представляющими одноразовые задачи, а затем создает Pods для выполнения этих задач до завершения.
- Endpoints controller. Заполняет объект Endpoints (то есть соединяет Services & Pods)
- Service Account & Token controllers. Создает учетные записи по умолчанию и токены доступа API для новых namespaces
### 1.5 Cloud Controller Manager



##2. Node(worker)
Управляется Control Plane(master) и имеет локальные демоны и сервисы, которые запускают Pod. 
Компоненты:
- kubelet
- container runtime
- kube-proxy

