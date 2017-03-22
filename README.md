# MAP-API<br/>
由于早期地图插件不支持https，这次使用高德地图API。<br/>
高德地图API：http://lbs.amap.com/api/javascript-api/summary<br/>

*注册成为高德开发者需要分三步：<br/>

        第一步，注册高德开发者；
        第二步，去控制台创建应用；
        第三步，获取Key。

## 构建地图<br/>

	var map = new AMap.Map('container', {
                resizeEnable: true,
                zoom:11,
                center: [116.397428, 39.90923]
         });
	 
<br/>
## 加载定位插件（由ip定位当前城市）<br/>

        map.plugin('AMap.CitySearch', function() {showCityInfo()}); //加载由ip搜索地区的插件
	        //获取用户所在城市信息
	        function showCityInfo() {
	                //实例化城市查询类
	                var citysearch = new AMap.CitySearch();
	                //自动获取用户IP，返回当前城市
	                citysearch.getLocalCity(function(status, result) {
	                if (status === 'complete' && result.info === 'OK') {
	                        if (result && result.city && result.bounds) {
	                        var GDcityinfo = result.city;
	                        var citybounds = result.bounds;
	                        console.log('您当前所在城市：'+GDcityinfo);
	                        //地图显示当前城市
	                        map.setBounds(citybounds);
	                        }
	                } else {
	                        console.log(result.info);
                        }
                });
	    }
         
 
