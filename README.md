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
docker volume create puppeteer-vol
docker run --cap-add=SYS_ADMIN --mount src=puppeteer-vol,dst=/workspace -w /workspace -it puppeteer:latest bash
````

とすればvolumeの永続化もできる

```sh
yarn add puppeteer
```

```js
// hello.js
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```

```sh
node hello.js
```
