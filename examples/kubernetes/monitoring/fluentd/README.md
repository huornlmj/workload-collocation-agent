### DEBUGGING

```bash
kubectl delete ds --all -n fluentd ; kubectl delete cm --all -n fluentd
kubectl apply -k . -n fluentd ; k -n fluentd rollout status ds fluentd
while sleep 1 ; do kubectl -n fluentd logs --tail 5 --follow `kubectl get pods -owide -n fluentd |grep node14 | awk '{print $1}'`; done
curl 100.64.176.40:24231/metrics
```


