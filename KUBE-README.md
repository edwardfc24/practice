# ¿Qué es Kubernetes?

> **Kubernetes** (abreviado como **K8s**) es una plataforma de código abierto para **automatizar el despliegue, escalado y gestión de aplicaciones en contenedores**.

Creado por Google y ahora mantenido por la CNCF, Kubernetes está diseñado para facilitar la ejecución de aplicaciones complejas en entornos distribuidos, ya sea en la nube, on-premise o híbridos.

---

## Componentes básicos de Kubernetes

| Componente        | Descripción breve                                                                 |
|-------------------|----------------------------------------------------------------------------------|
| **Pod**           | Unidad mínima de ejecución. Puede contener uno o varios contenedores.            |
| **Node**          | Máquina física o virtual que ejecuta Pods. Hay nodos workers y master/control.   |
| **Deployment**    | Declaración deseada del estado de la app (número de pods, imagen, etc.).          |
| **Service**       | Abstracción de red que expone un conjunto de Pods como un servicio estable.       |
| **Namespace**     | Segmenta recursos lógicamente dentro del clúcster.                                 |
| **ConfigMap/Secret** | Almacenan configuraciones o secretos para las apps.                            |
| **Volume**        | Almacenamiento persistente para los Pods.                                        |

---

## Ciclo de vida de una app en Kubernetes

1. Se escribe un manifiesto YAML (por ejemplo, un `Deployment`).
2. Se aplica con `kubectl apply -f archivo.yml`.
3. Kubernetes programa los Pods en los nodos.
4. Se expone con un `Service` si es necesario.
5. El sistema mantiene el estado deseado: si un Pod cae, lo recrea.

---

## Comandos básicos de Kubernetes (`kubectl`)

| Comando                                | Descripción                                                   |
|----------------------------------------|----------------------------------------------------------------|
| `kubectl get pods`                     | Lista los Pods en ejecución                                   |
| `kubectl get deployments`              | Muestra los deployments activos                               |
| `kubectl get services`                 | Lista los servicios expuestos                                 |
| `kubectl apply -f archivo.yaml`        | Aplica una definición desde un archivo YAML                   |
| `kubectl delete -f archivo.yaml`       | Elimina los recursos definidos en el archivo                  |
| `kubectl logs <pod>`                   | Muestra los logs de un Pod                                    |
| `kubectl exec -it <pod> -- bash`       | Accede de forma interactiva a un contenedor dentro del Pod    |
| `kubectl describe <resource> <name>`   | Describe detalles de un recurso (eventos, estado, etc.)       |
