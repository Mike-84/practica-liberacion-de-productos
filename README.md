# Práctica liberación de productos

Para arrancar prometheus se arrancará por k8s, entonces utilizando kubectl apply -f prometheus.yaml crearíamos los servicios y kubectl apply -f grafana.yaml si queremos otro utilizar el visualizador de métricas que no sea el de prometheus que viene por defecto.

Pasos para vincular grafana con prometheus:

 - Crear un data sources de prometheus.

 - Una vez seleccionado la pestaña prometheus en la pestaña URL ponemos http://prometheus-server:80, esto solo funciona si están en el mismo namespace, o se podría poner con .default Ej.: http://prometheus-server.default:80, el .default es el namespace en el que esta el servidor de prometheus, o usando el cluster-ip para verlo se tendría que ver desde la consola donde levantaste el prometheus y poner kubectl get svc y te pondrán todos los servicios con su respectivo cluster-ip.

 - Darle save & test que guardará y probará que la URL es correcta.

Para cargar el json solo hay que ir al simbolo +, darle a import y pinchar en upload JSON file. Con esto te cargará un dasboard llamado "Práctica grafana dashboard". 
