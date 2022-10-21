# Скачать презентацию с etest в виде pdf

---

## [На скачанные pdf можно наложить текст тут](https://agile-garden-12289.herokuapp.com/)


## Инструкция

1. Открыть страницу с презентацией
3. Скопировать строку ниже
~~~~
avascript:(()=>{window.require=null,window.define=null;const e=document.querySelector("h2")?.innerText?.replace(/Лекция[.]?/g,"")?.trim()||"безымянный.pdf",t=document.createElement("script");function n(e){return new Promise((function(t,n){const o=document.createElement("img");o.src="data:img/png;base64,"+e,o.onload=function(){t({w:o.width,h:o.height})}}))}t.src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.4.0/jspdf.umd.min.js",t.async=!1,document.head.appendChild(t),t.onload=async()=>{const t=await async function(){return new Promise(((t,n)=>{console.log(1);const o=new XMLHttpRequest;document.body.className="",document.body.id="",document.body.innerHTML=`<progress id="indicator" style="width: 50%;"></progress><h1>Скачиваем ${e}</h1><div id="progress">Скачано: 0 Bytes</div>`;const d=document.querySelector("#progress"),r=document.querySelector("#indicator");o.onloadend=()=>{r.value="100",r.max="100",t(o.response)},o.onprogress=e=>{console.log(e),d.innerText="Скачано "+function(e,t=2){if(!+e)return"0 Bytes";const n=1024,o=t<0?0:t,d=["Bytes","KB","MB","GB","TB","PB","EB","ZB","YB"],r=Math.floor(Math.log(e)/Math.log(n));return`${parseFloat((e/Math.pow(n,r)).toFixed(o))} ${d[r]}`}(e.loaded)},o.open("GET",window.location.href,!0),o.send()}))}(),o=document.createElement("div");console.log(t),o.innerHTML=t;const d=[...o.querySelectorAll("slide")],r=d.map((e=>e.getAttribute("data"))),s=new jspdf.jsPDF;s.deletePage(1);const a=await Promise.all(r.map(n));d.map((e=>e.getAttribute("data"))).forEach(((e,t)=>{const{w:n,h:o}=a[t];s.addPage([n,o],"l"),s.addImage(e,null,0,0,n,o)}),s),s.output("save",e+".pdf")}})();
~~~~
4. Вставить ее в адресную строку на странице с презентацией
5. Ввести j в начало строки чтобы получилось как на картинке
   ![img_1.png](img_1.png)
6. Нажать Enter и ждать. Презентация скачается без индикатора загрузки
