## Симптом (что произошло)
БД - PostgreSQL не отвечает. В Postman код ошибки 503, в DBeaver - connection attempt failed

## Предмет проверки и порядок действий
1. docker ps -a — статус Exited (137)
2. journalctl -u docker.service --no-pager | grep <ID_контейнера_pg>

## Что не подтвердилось
Не проверялось отдельно — причина нашлась сразу через docker ps -a

## Причина инцидента
Контейнер pg был принудиnтельно завершен, статус Exited (137). Подтвердил через journalctl -u docker.service: поле hasBeenManuallyStopped=true показывает, что остановка была инициирована вручную

## Как устранил инцидент
docker start pg, проверка через Postman и DBeaver

## Как избежать инцидент в будущем
Ввести алерт с оповещением для pg, чтобы узнавать о падении своевременно, а не по жалобе из Postman
