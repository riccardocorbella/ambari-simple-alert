# ambari-simple-alert
The aim of this project is to show how to create a custom alert backed up by a python script in Ambari.

Steps to follow:
1. copy the py script in the dir /var/lib/ambari-server/resources/host_scripts/ on the ambari server host.;
2. create the alert on ambari: **curl -u [usename]:[password] -i -H 'X-Requested-By: ambari' -X POST -d @alert.json http://localhost:8080/api/v1/clusters/[cluster_name]/alert_definitions**;
3. get the id of the alert: **curl -u [usename]:[password] -i -H 'X-Requested-By: ambari' -X GET http://localhost:8080/api/v1/clusters/[cluster_name]/alert_definitions**;
4. force the alert to run: **curl -u admin:admin -i -H 'X-Requested-By: ambari' -X PUT http://localhost:8080/api/v1/clusters/[cluster_name]/alert_definitions/[alert id]?run_now=true**;
