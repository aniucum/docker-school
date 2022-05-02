- создаём сеть
```
docker network create -d bridge back-db
```
![task 02 01.img](/task-02/img/01.JPG)
- запускаем базу
```
docker run -d --rm --name database \
           -e POSTGRES_USER=django \
           -e POSTGRES_PASSWORD=django \
           -e POSTGRES_DB=django \
           -v $(pwd)/data/db:/var/lib/postgresql/data \
          --network="back-db" \
           postgres:13.6
```
![task 02 02.img](/task-02/img/02.JPG)
- собираем бэк
```
docker build -t back .
```
![task 02 04.img](/task-02/img/03.JPG)
![task 02 04.img](/task-02/img/04.JPG)
- запускаем
```
docker run -d --rm --name back \
           -p 8000:8000 \
          --network="back-db" \
           back
```
![task 02 05.img](/task-02/img/05.JPG)
![task 02 06.img](/task-02/img/06.JPG)
