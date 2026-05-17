Симптомы: пользователи получают 5xx/timeout, в Grafana растёт время ответа и/или error rate.

Быстрые проверки: проверить Pods, события, логи приложения, метрики в дашборде. Если после последнего деплоя начались ошибки — выполнить rollback. Если явного изменения не было — безопасно перезапустить Deployment.
```
kubectl -n <namespace> get pods -o wide
kubectl -n <namespace> describe pod <pod-name>
kubectl -n <namespace> logs deploy/<deployment-name> --since=10m
kubectl -n <namespace> rollout status deploy/<deployment-name>
kubectl -n <namespace> rollout restart deploy/<deployment-name>

kubectl -n <namespace> rollout undo deploy/<deployment-name>
```
