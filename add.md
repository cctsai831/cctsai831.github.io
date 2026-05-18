# Jupyter Notebook in Browser

假設已經使用
```
docker run --gpus all --shm-size 128G --name foo -v /path/to/where/u/want/to/start:/workspace -ti docker/image/name/or/ID bash
```
run 一個 docker container。首先，要找到此容器的 `IPAddress`，藉由
```
docker inspect foo | grep "IPAddress"
```
再來，執行
```
docker attach foo
```
進入到容器內，以
```
pip list | grep notebook
```
確認 notebook 有被安裝到正確版本（即 6.5.7），然後執行
```
jupyter notebook --no-browser --ip 0.0.0.0 --allow-root
```
只要看到
```
Jupyter Notebook 6.5.7 is running at:
```
顯示在終端機就可以開啟另一個終端機繼續進行。在另一個終端機上，先執行
```
ssh -NL 1111:IPAddress:8888 user@remote/server/IP
```
然後在本地端開啟 Google Chrome 並輸入
```
localhost:1111
```
如果看到
```
Token authentication is enabled
```
且要求輸入 Password or Token，則在前一個終端機中找到
```
token=xxxxxxxxxxzzzzzzzzzz
```
並將 `xxxxxxxxxxzzzzzzzzzz` 依照要求輸入，至此結束。
