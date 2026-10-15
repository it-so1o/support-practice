# support-practice
## О проекте
Учебный стенд на моём ноутбуке, самообучение после прохождения курса Инженер сопровождение L2. 

## Из чего состоит стенд 
- VirtualBox, Ubuntu Server 24.04
- Docker
- Nginx — принимает запросы на порт 80 и передаёт их в PostgREST (обратный прокси)
- PostgREST
- PostgreSQL
- Prometheus
- Grafana
- Экспортеры

## Как идет запрос
- запрос → Nginx (порт 80) → PostgREST (порт 3000) → PostgreSQL (порт 5432)

## Инциденты
Разборы лежат в папке incidents».
