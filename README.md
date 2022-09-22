# Dataiku docker cuda 11.6.2


### Run on docker with Nvidia support


```
docker volume create dss

docker run --gpus all -d -it -p 10000:10000 --name dss \
    --restart=unless-stopped \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v dss:/root \
    --user dataiku \
    ejtrader/dss:gpu

```

### Run on docker without Nvidia Support



```
docker volume create dss

docker run --gpus all -d -it -p 10000:10000 --name dss \
    --restart=unless-stopped \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v dss:/root \
    --user dataiku \
    ejtrader/dss:cpu

```