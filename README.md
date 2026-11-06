# Datakit objetos



## Antes de instalar el Datakit

Es necesario instalar y seguir los pasos de este otro datakit, el cual contiene las conexiones

https://github.com/fatimafer/DC_connections.git  


## Instalar el Datakit

Abrimos en el navegador el Playground de Data 360 que hemos creado en el paso anterior.
Abrimos un terminal que tenga Salesforce CLI instalado, preferentemente en VSCODE


Nos conectamos al playground creado en el paso anterior.
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


## Si vemos errores, existe un bug Data Governance, policy All Data Access Ruleset
Vamos a la pestaña de Data Governance
![alt text](images\Data_governance.png)

Hacemos click en Policies
![alt text](images\policies.png)

Eliminamos All Data Access Ruleset
![alt text](images\Alldataaccess.png.png)

En el botón superior derecho hacemos click en New
![alt text](images\new.png)

En el panel izquierdo seleccionamos Data Access y después next
![alt text](images\Newpolicy.png)

Creamos una nueva policy que permita el acceso a todo seleccionando estas opciones
![alt text](images\viewall.png)
![alt text](images\allusers.png)


Pulsamos el botón superior derecho que indica Save and activate
![alt text](images\save.png)