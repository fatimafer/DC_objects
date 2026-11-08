# Datakit objetos



## Antes de instalar el Datakit

Es necesario instalar y seguir los pasos de este otro datakit, el cual contiene las conexiones

https://github.com/fatimafer/DC_connections.git  


## Instalar el Datakit

Abrimos en el navegador el Playground de Data 360 que hemos creado en las instrucciones del repositorio anterior.
Abrimos un terminal que tenga Salesforce CLI instalado, preferentemente en VSCODE.

Clonamos el respositorio y nos situamos en la carpeta donde lo hemos clonado
```
https://github.com/fatimafer/DC_objects.git
```
```
cd DC_objects
```


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

## Pasos posteriores

### Lanzar los Datastreams de AWS y GCLOUD

* Vamos a la pestaña de Data Streams

    ![alt text](images/Data_streams.png)


* Lanzamos los Datastreams reservations_suite, reservations_deluxe, reservations_standard y guest. Para ello hacemos click en la flecha y en refresh now

    ![alt text](images/Refresh_now.png)

* Seleccionamos full refresh y hacemos click en Refresh Now

    ![alt text](images/fullrefresh.png)

* Esperamos a que Last Run Status cambie a Success

    ![alt text](images/Success.png)


### Lanzar Identity Resolution

* Vamos a la pestaña de Identity Resolution

    ![alt text](images/resolution.png)


* Seleccionamos Resolution based on Email and name

    ![alt text](images/resolution_based.png.png)


* Hacemos click en el botón superior derecho llamado Run Ruleset

    ![alt text](images/ruleset.png)


* Esperamos a que Last job Status estado cambie a Succeeded

    ![alt text](images/sucecced.png)


### Lanzar Calculated Insight

* Vamos a la pestaña de Calculated Insight

    ![alt text](images/CI.png)


* En la flecha de la parte derecha hacemos click en Run now

    ![alt text](images/CI.png)


* Esperamos a que Last Run Status cambie a Success

    ![alt text](images/CISucess.png)




## Si vemos errores, existe un bug Data Governance, policy All Data Access Ruleset

* Vamos a la pestaña de Data Governance

    ![alt text](images/Data_governance.png)

* Hacemos click en Policies

    ![alt text](images/policies.png)

* Eliminamos All Data Access Ruleset

    ![alt text](images/Alldataaccess.png.png)

* En el botón superior derecho hacemos click en New

    ![alt text](images/new.png)

* En el panel izquierdo seleccionamos Data Access y después next

    ![alt text](images/Newpolicy.png)

* Creamos una nueva policy que permita el acceso a todo seleccionando estas opciones

    ![alt text](images/viewall.png)
    ![alt text](images/allusers.png)


* Pulsamos el botón superior derecho que indica Save and activate

    ![alt text](images/save.png)