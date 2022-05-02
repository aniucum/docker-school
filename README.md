```
docker build -t frontend -f Dockerfile-frontend . && \
docker tag frontend localhost:5000/frontend && \
docker push localhost:5000/frontend
```

```
docker build -t backend -f Dockerfile-backend . && \
docker tag frontend localhost:5000/backend && \
docker push localhost:5000/backend
```
docker compose up -d
docker compose down --remove-orphans
