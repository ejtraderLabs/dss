
![example workflow](https://github.com/ejtraderLabs/dss/actions/workflows/main.yml/badge.svg)

# Dataiku docker cuda 11.7.0


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

docker run -d -it -p 10000:10000 --name dss \
    --restart=unless-stopped \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v dss:/root \
    --user dataiku \
    ejtrader/dss:cpu

```

#### Acess web gui

```
http://localhost:10000/

```


### To build image from source

#### clone repository

```
git clone https://github.com/ejtraderLabs/dss
cd dss
```

#### For GPU
```
docker build --build-arg dssVersion=11.0.2 -t ejtrader/dss:gpu -f Dockerfile-gpu .

```

#### For CPU

```
docker build --build-arg dssVersion=11.0.2 -t ejtrader/dss:cpu -f Dockerfile-cpu .

```
