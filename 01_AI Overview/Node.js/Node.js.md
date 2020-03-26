```
asynchronous 异步
```
## 关于Node.js 的介绍
作为一个异步时间驱动的JavaScript运行时，Node.js的设计主要用于建立可扩展的网络应用。在下列的"hello world"案例中，许多连接可以同时处理,每个连接都会处理回调，但是如果没有工作要做，Node.js会进入睡眠状态。

```
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req,res)) =>{
    res.statusCode = 200;
    res.setHeader('Content-Type','text/plain');
    res.end('Hello World');

}

server.listen(port,hostname,()=>{
    console.log('Server running at http://${hostname}:${port}/`);
}


)
```

这与当今常见的并发模型不同，后者使用OS线程。基于线程的网络效率相对较低，并且很难使用。此外，Node.js的用户无需担心锁死该进程，因为没有锁。Node.js中几乎没有功能直接执行I/O,因此该过程永远不会堵塞。因为没有障碍，所以在Node.js中开发科伸缩系统非常合理。

如果这个语言你不熟悉，择优完整的文章介绍"阻塞与非租塞"