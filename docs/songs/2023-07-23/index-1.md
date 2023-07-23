---
lastUpdated: true
contributors: true
externalLinkIcon: false
date: 2023-07-23
---
# Přehled klíčových objektů v Kubernetes (K8S)

![Kubernetes Logo](https://www.example.com/k8s_logo.png)

Kubernetes (známý také jako K8S) je populární open-source platforma pro orchestraci kontejnerů. Jeho hlavním cílem je usnadnit správu, nasazení a škálování kontejnerových aplikací. Abychom pochopili, jak Kubernetes dosahuje těchto cílů, je důležité se seznámit s jeho klíčovými objekty. Tyto objekty definují stav a chování aplikací a služeb v Kubernetes clusteru.

## 1. Pod

Pod je nejmenší a základní nasaditelnou jednotkou v Kubernetes. Reprezentuje jednu nebo více spolu provázaných kontejnerů, které sdílejí síť a úložiště na stejném pracovním uzlu. Pod poskytuje izolaci zdrojů pro kontejnery uvnitř něj, což umožňuje, aby mohly spolu komunikovat a sdílet data. Pod je dočasná entita, což znamená, že jej lze snadno vyměnit nebo znovu vytvořit.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: mojepod
spec:
  containers:
  - name: kontejner1
    image: nginx:latest
  - name: kontejner2
    image: busybox:latest
```

## 2. Deployment

Deployment abstrahuje a zjednodušuje správu replik Podů. Zajišťuje, že počet replik kontejnerů odpovídá požadovanému stavu, což zajišťuje dostupnost a škálovatelnost aplikace. Deployment umožňuje snadnou aktualizaci aplikace na novou verzi bez výpadku služby. Pokud chceme změnit stav aplikace nebo provést aktualizaci, stačí upravit specifikaci Deploymentu.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mojedeployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: mojeaplikace
  template:
    metadata:
      labels:
        app: mojeaplikace
    spec:
      containers:
      - name: kontejner
        image: mojeaplikace:1.0
```

## 3. Service

Service umožňuje komunikaci mezi kontejnery uvnitř Kubernetes clusteru. Jedná se o abstrakci, která definuje stálý bod přístupu k jednomu nebo více podům. Existují různé typy Service, například ClusterIP, NodePort nebo LoadBalancer, které určují způsob, jakým služba bude přístupná.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: mojesluzba
spec:
  selector:
    app: mojeaplikace
  ports:
  - protocol: TCP
    port: 80
    targetPort: 8080
```

## 4. ConfigMap a Secret

ConfigMap a Secret umožňují oddělení konfigurace od kontejnerových obrazů. ConfigMap obsahuje konfigurační data jako klíče a hodnoty, které jsou použity v aplikaci. Secret je obdobný ConfigMap, ale používá se pro ukládání citlivých údajů, jako jsou hesla nebo certifikáty, v zašifrované podobě.

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: mojeconfigmap
data:
  konfigurace1: hodnota1
  konfigurace2: hodnota2
```

## 5. PersistentVolume a PersistentVolumeClaim

PersistentVolume (PV) je reprezentace fyzického úložiště v Kubernetes clusteru. Poskytuje abstrakci pro ukládání dat oddělenou od konkrétního úložiště. PersistentVolumeClaim (PVC) slouží k rezervaci místa na PersistentVolume.

```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: mojepersistentvolume
spec:
  capacity:
    storage: 5Gi
  accessModes:
  - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  storageClassName: slow
```

## Závěr

Kubernetes nabízí širokou škálu klíčových objektů, které umožňují správu, nasazení a škálování kontejnerových aplikací. Pod, Deployment, Service, ConfigMap, Secret, PersistentVolume a další objekty společně tvoří základní stavební kameny Kubernetes. Díky nim lze vytvářet robustní, vysokodostupné a snadno spravovatelné aplikace v kontejnerovém prostředí.

Tento přehled klíčových objektů v Kubernetes by vám měl poskytnout základní povědomí o jejich účelu a použití. Pokud chcete pokračovat v objevování Kubernetes, existuje mnoho dalších aspektů a pokročilých funkcí, které si můžete prozkoumat.

---
Toto je základní verze článku. Můžete ho dále upravit, přidat další informace, příklady nebo rozšířit jednotlivé sekce, aby byl co nejkompletnější a snadno srozumitelný pro vaše čtenáře. 