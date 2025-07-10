# otus_project
Для того, чтоб развернуть кластер потребуеться выполнить:
- Заполнить secrets в github а именно
  - SSH_PASSWORD
  - SSH_USER
  - SSH_PORT
- После этого запустить выполнение пайплайна

## Процесс
- Пайплайн подключится к машине по ssh
- Установить необходимые пакеты в систему
- Склонирует 2 репозитория, kubespray и otus_proj
- Раскатает кластер по инвентарю и настройкам из директории otus-cluster
- Установит приложение argocd в кластер, а именно в namespace argocd
- Добавит helm repo для ingress и установит его
- Применит манифест для argocd app-of-apps
- Argocd развернет все необходимые приложения а именно:
  - grafana
  - loki
  - promtail
  - google online boutique
