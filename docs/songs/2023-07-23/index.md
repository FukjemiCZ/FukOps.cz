---
contributors: false
externalLinkIcon: true
date: 2023-07-23
---
# Základní objekty
V Kubernetes existuje několik základních objektů, které slouží k definici stavu a chování aplikací a služeb v clusteru. Tyto objekty popisují kontejnery, jejich konfigurace, požadavky na zdroje, služby, síťová pravidla a další aspekty potřebné pro nasazení a provoz aplikací. Zde je seznam některých základních objektů v Kubernetes:

1. **Pod**: Nejmenší a základní nasaditelná jednotka v Kubernetes. Reprezentuje jednu nebo více spolu provázaných kontejnerů, které sdílejí síť a úložiště na stejném pracovním uzlu.

2. **Deployment**: Slouží k deklarativnímu definování požadovaného stavu aplikace. Umožňuje snadnou aktualizaci aplikace a zajišťuje, aby počet replik kontejnerů byl konzistentní.

3. **ReplicaSet**: Zajišťuje, že počet replik podů odpovídá požadovanému stavu, který je určen ve specifikaci. Deployment vlastně používá ReplicaSet pro provoz kontejnerů.

4. **StatefulSet**: Podobně jako Deployment, ale navíc udržuje pořadí a unikátní jména pro každý pod. Často používán pro ukládání dat a aplikace, které vyžadují pevný identifikátor v síti.

5. **DaemonSet**: Zajišťuje, že každý pracovní uzel v clusteru má jednu repliku podu z daného nastavení. Ideální pro přidání démonů nebo síťových služeb na každý uzel.

6. **Job**: Reprezentuje úlohu nebo proces, který je potřeba spustit a úspěšně dokončit. Joby jsou často používány pro úlohy s konkrétním začátkem a koncem.

7. **CronJob**: Podobně jako Job, ale umožňuje plánovat opakované úlohy na základě určitého časového plánu (cron-like).

8. **Service**: Abstrakce, která definuje stálý bod přístupu k jednomu nebo více podům. Služby umožňují kontejnerům komunikovat mezi sebou a s vnějším světem.

9. **Ingress**: Umožňuje přístup k aplikaci z vnějšku clusteru. Definuje pravidla směrování pro připojení k různým službám.

10. **ConfigMap**: Umožňuje oddělit konfiguraci od kontejnerových obrazů. Obsahuje konfigurační data jako klíče a hodnoty, které jsou použity v aplikaci.

11. **Secret**: Slouží k uchování citlivých údajů, jako jsou hesla nebo certifikáty, v zašifrované podobě.

12. **PersistentVolume (PV)**: Reprezentuje fyzické úložiště v clusteru a poskytuje abstrakci pro ukládání dat.

13. **PersistentVolumeClaim (PVC)**: Žádost o určitý objem úložiště. Vytvořením PVC je možné rezervovat místo na PersistentVolume.

Toto je pouze základní seznam objektů, které Kubernetes nabízí. Existují i další rozšířené objekty nebo možnosti pro správu a konfiguraci aplikací a služeb v Kubernetes clusteru.