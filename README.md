# Dataiku docker cuda 11.6.2


### Run on docker with Nvidia support

```
docker run --gpus all -d -it -p 10000:10000 -v $(pwd)/data:/root  --user dataiku ejtrader/dss 

```

### Run on docker without Nvidia Support



```
docker run -d -it -p 10000:10000 -v $(pwd)/data:/root  --user dataiku ejtrader/dss \

```