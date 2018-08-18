
# vue-cli `vue init webpack` 项目添加 prerender-spa-plugin

## 1. 使用history模式

```
export default new Router({
  mode: 'history',
  ...
})


```
### nginx的配置


```
location / {
  try_files $uri $uri/ /index.html;
}
```

## 2. main.js

```
new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>',
  mounted () {
    // You'll need this for renderAfterDocumentEvent.
    document.dispatchEvent(new Event('render-event'))
  }
})
```

## 3. 给`webpack.prod.conf.js`添加插件
安装

```
npm i prerender-spa-plugin -D
```


```
const PrerenderSPAPlugin = require('prerender-spa-plugin')

```


```
  // vue预渲染
    new PrerenderSPAPlugin({
      // Required - The path to the webpack-outputted app to prerender.
      staticDir: path.join(__dirname, '../dist'),
      // Required - Routes to render.
      routes: [  '/about' ],
    })
```

4. 现在试试npm run build 打包
