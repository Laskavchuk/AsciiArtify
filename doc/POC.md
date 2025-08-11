# Proof of Concept — Доступ до ArgoCD UI

## 1. Перевірка стану кластеру
```bash
kubectl get nodes
kubectl get pods -n argocd
```
## 2. Проброс порту
``` bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## 3. Отримання паролю адміністратора
```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
```

## 4.Вхід у веб-інтерфейс
- Відкрити браузер: https://localhost:8080
- Логін: admin
- Пароль: (з попереднього кроку)

## Відео-демонтсрація
