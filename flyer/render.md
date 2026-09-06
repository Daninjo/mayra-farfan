# Regenerar flyer y OG

Se renderiza con Chrome headless vía puppeteer-core (viewport exacto). Script de referencia:

```js
// node shot.js <url> <w> <h> <out.png|out.pdf> [fullPage=1]
const puppeteer=require('puppeteer-core');
(async()=>{const [url,w,h,out,full='1']=process.argv.slice(2);
const b=await puppeteer.launch({executablePath:'/Applications/Google Chrome.app/Contents/MacOS/Google Chrome',headless:true});
const p=await b.newPage();await p.setViewport({width:+w,height:+h});
await p.goto(url,{waitUntil:'networkidle0'});await p.evaluate(()=>document.fonts.ready);
if(out.endsWith('.pdf'))await p.pdf({path:out,printBackground:true,preferCSSPageSize:true});
else await p.screenshot({path:out,fullPage:full==='1'});await b.close();})();
```

```
node shot.js file://$PWD/flyer/flyer.html 1080 1350 flyer/flyer-wa.png 0
node shot.js file://$PWD/flyer/flyer.html 1080 1350 flyer/flyer-a5.pdf 0
node shot.js file://$PWD/flyer/og.html 1200 630 og.png 0   # luego convertir a og.jpg
```

QR: `segno.make("https://daninjo.github.io/mayra-farfan/?src=flyer_qr", error='m')`.
