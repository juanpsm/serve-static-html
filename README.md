## Probando con kind

Simplificamos las pruebas usando un cluster kind que a su vez luego
aprovisionamos con helmfile. Para ello ingresar en la carpeta [`kind`](./kind/).

En este mismo directorio, proveemos un `.envrc` que setea la variable
`KUBECONFIG` para que kind trabaje en este directorio.

Procedemos entonces a crear un cluster kind:

```bash
kind create cluster
```

Luego, instalamos las herramientas necesarias con helmfile:

```bash
helmfile apply
```

Port forward para acceder desde el navegador:

```bash
kubectl port-forward svc/test-serve-static 8080:80
```
