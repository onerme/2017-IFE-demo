
# 网页抓取分析服务系列之三（服务封装）

## 任务目的
- 学习NodeJS HTTP模块
- 学习NodeJS和本地进程的互动
- 学习NodeJS和mongodb的交互
## 任务描述
- 安装nodejs和mongodb
- 利用nodejs的HTTP模块封装一个node服务，监听8000端口，接受一个参数（关键字），http模块示例参考如下：

``` javascript
   var http = require("http");  
   http.createServer(function(request, response) {  
           console.log('request received');  
           response.writeHead(200, {"Content-Type": "text/plain"});  
           response.write("Hello World");  
           response.end();  
   }).listen(8000);  
   console.log('server started');
```


- 收到请求后，启动phantomjs进程执行taskjs，并将接受到的参数传递给phantomjs
- phantomjs执行完后告诉node服务，并传回抓取的json结果
- node服务将结果存到mongodb中（使用mogoose）
## 任务注意事项
- 参考nodejs和mongodb的相关文档快速学习和实践
## 学习资料
- [nodejs安装][1]
- [nodejs 实现一个http server][2]
- [nodejs http模块API][3]
- [mongodb安装][4]
- [mongodb 介绍][5]
- [mongoose][6]


  [1]: https://nodejs.org/en/download/
  [2]: http://jobar.iteye.com/blog/2083843
  [3]: https://nodejs.org/dist/latest-v6.x/docs/api/http.html#http_http_createserver_requestlistener
  [4]: https://www.mongodb.com/download-center?jmp=nav
  [5]: http://www.runoob.com/mongodb/mongodb-tutorial.html
  [6]: http://www.nodeclass.com/api/mongoose.html