# puppeteer

https://github.com/GoogleChrome/puppeteer/blob/master/docs/troubleshooting.md#running-puppeteer-in-docker

を参考に、Dockerfile化したプロジェクト

## 利用方法

```sh
docker build -t puppeteer:latest .
docker run --cap-add=SYS_ADMIN -it puppeteer:latest bash
pptruser@hostname:vim hello.js
```

でbashを立ち上げvimで編集


```sh
docker build -t puppeteer:latest .
docker volume create puppeteer-project
docker run --cap-add=SYS_ADMIN --mount src=puppeteer,dst=/workspace -w /workspace -it puppeteer:latest bash
````

とすればvolumeの永続化もできる
