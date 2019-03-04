# Tick Stack with grafana 
### Tick with jolokia agent for spring-boot apps

Teststed On opebhsift V3.11 with Centos OS 7.6

Note: Chnage the mail password at grafana-template.yaml  before applying yaml files


`oc new-project tick`

`oc adm policy add-scc-to-user anyuid -z default -n tick`

`oc adm policy add-scc-to-user anyuid -n tick z default`

`oc adm policy add-scc-to-user privileged -z default -n tick`

`oc adm policy add-cluster-role-to-user cluster-admin -n tick -z default`

`oc process -f influxd/influxdb-template.yaml | oc create -f -`

`oc process -f telegraf/telegraf-template.yaml | oc create -f -`

`oc process -f chronograf/chronograf-template.yaml | oc create -f -`

`oc process -f grafana/grafana-template.yaml | oc create -f -`

`oc process -f kapacitor/kapacitor-template.yaml | oc create -f -`

`oc create -f tick-ingress-admin.yaml`

`oc create -f tick-ingress.yaml`

#### Allow Pod newtwoek between projects 

`oc adm pod-network make-projects-global dev tick`