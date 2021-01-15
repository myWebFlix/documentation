### Etcd variables

webflix: maintenance-mode, broken
users: disable-login
comments: disable-user-info, disable-comments-submit

```
kubectl exec --stdin --tty etcd-deployment-d6d87d6dc-n9mtj -- etcdctl --endpoints http://0.0.0.0:2379 set /environments/dev/services/comments-service/1.0.0/config/rest-config/disable-user-info true
```

### Logging queries

https://dashboard.logit.io/a/eb64325f-3de5-438f-a0e5-e1dac029cb0e/s/7c6b0d90-1d93-479b-afd2-2192236ca571/kibana/access

```
marker.name: ENTRY or marker.name: EXIT
contextMap.logTracerUuid: LOG_TRACER_UUID and (marker.name: ENTRY or marker.name: EXIT)
contextMap.method: getVideoMetadata and marker.name: ENTRY
contextMap.applicationName: webflix and marker.name: ENTRY
```

### Liveness

```
rok.zoxxnet.com/webflix/health/live
```

### Metrics 

http://rok.zoxxnet.com/video-stream/metrics/application
http://rok.zoxxnet.com/webflix/metrics/application
