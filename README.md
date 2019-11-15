# puppeteer

https://github.com/GoogleChrome/puppeteer/blob/master/docs/troubleshooting.md#running-puppeteer-in-docker

を参考に、Dockerfile化したプロジェクト

## 利用方法

```sh
docker run --cap-add=SYS_ADMIN -it puppeteer:latest bash
```

でbashで編集

```sh
docker image create puppeteer-project
docker run --cap-add=SYS_ADMIN --mount src=puppeteer,dst=/workspace -w /workspace -it puppeteer:latest bash
````
とすればvolumeを永続化できる
