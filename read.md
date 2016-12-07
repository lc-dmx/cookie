
* [Apache下载](http://zhinan.sogou.com/guide/detail/?id=1610018585)

* [Apache配置](http://jingyan.baidu.com/article/acf728fd437389f8e410a35f.html)
##演示地址
###因为本地地址无法访问，所以切换到了sina SAE上
* [代码演示](http://5.lcdmx.applinzi.com/)

```
//计数器
	var cookieCount = {}; 
	cookieCount.count = function () { 
		var count = parseInt(this.getCount('myCount')); 
		count++; 
		document.cookie = 'myCount=' + count + ''; 
		alert('第'+count+'访问'); 
	} 

	cookieCount.setCount= function () { 
		//首先得创建一个名为myCount的cookie 
		var expireDate = new Date(); 
		expireDate.setDate(expireDate.getDate()+1); 
		document.cookie = 'myCount=' + '0' +';expires=' + expireDate.toGMTString(); 
	} 
	
	cookieCount.getCount = function (countName) { 
		//获取名为计数cookie,为其加1 
		var arrCookie = document.cookie.split('; '); 
		var arrLength = arrCookie.length; 
		var ini = true; 
		for(var i=0; i<arrLength; i++) { 
			if(countName == arrCookie[i].split('=')[0]){ 
				return parseInt(arrCookie[i].split('=')[1]); 
				break; 
			}else{ 
				ini = false; 
			} 
		} 
		if(ini == false)	this.setCount(); 
		return 0; 
	} 
	cookieCount.count(); 
```
