### I вариант
- запускам registry для образов
```
docker run -d -p 5000:5000 --name registry registry:2
```
собираем фронт и бэк
```
docker build -t frontend -f Dockerfile-frontend . && \
docker tag frontend localhost:5000/frontend && \
docker push localhost:5000/frontend
```
```
docker build -t backend -f Dockerfile-backend . && \
docker tag backend localhost:5000/backend && \
docker push localhost:5000/backend
```
- запускаем
```
docker compose up -d
```
![task 03 01.img](/task-03/img/01.JPG)
![task 03 02.img](/task-03/img/02.JPG)
- останавливаем
```
docker compose down --remove-orphans
```
### II вариант
- собираем
```
docker compose -f docker-compose-v2.yml build
```
![task 03 03.img](/task-03/img/03.JPG)
- запускаем
```
docker compose -f docker-compose-v2.yml up -d
```
