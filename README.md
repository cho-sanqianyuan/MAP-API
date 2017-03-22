# MAP-API<br/>
由于早期地图插件不支持https，这次使用高德地图API。<br/>
高德地图API：http://lbs.amap.com/api/javascript-api/summary<br/>

*注册成为高德开发者需要分三步：<br/>
第一步，注册高德开发者；<br/>
第二步，去控制台创建应用；<br/>
第三步，获取Key。<br/>

##构建地图<br/>
var map = new AMap.Map('container', {
        resizeEnable: true,
        zoom:11,
        center: [116.397428, 39.90923]
 });
