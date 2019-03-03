# Tick Stack with grafana 
### Tick with jolokia agent for spring-boot apps


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