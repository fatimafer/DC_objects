# Datakit objetos



## Antes de instalar el Datakit

Es necesario instalar y seguir los pasos de este otro datakit, el cual contiene las conexiones

https://github.com/fatimafer/DC_connections.git  


## Instalar el Datakit

Una vez realizados los pasos anteriores abrimos un terminal, preferentemente en VSCODE
```
git clone https://github.com/fatimafer/DC_cloud_objects.git
```
Si es otra terminal o no conectados a salesforce CLI, nos conectamos
```
sf org login web -s -a coral-cloud
```

Testeamos primero el despliegue
```
sf project deploy start --manifest manifest/package.xml --target-org coral-cloud --dry-run
```

Y si todo ha ido bien, desplegamos definitivamente
```
sf project deploy start --manifest manifest/package.xml --target-org coral-cloud
```