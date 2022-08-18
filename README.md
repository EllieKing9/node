# node
<h6>

```

2008 Google - Chrome - V8(JS engine) open : open source
2009 Ryan Dahl server side java script dev. : node.js
WEB -> Android, iOS 
sync -> async(event loop) : call back!
==> off loading 
  저수준의 오래 걸리는 일은 Node에게 (Node works low performance or take long time task)
  고수준의 로직은 메인 쓰레드에서
Node.js improves low perfomance binding C & WebAssembly(??) module
C : node-gyp
WebAssembly : ver. Node 12 more
npm : node.js packages

Deveploment Environment

online code editor : glitch (https://glitch.com/)
minimal node
ex) server.js
  const http = require('http')
  const server = http.createServer((req, res_ => {
    res.statusCode = 200
    res.end('Hello!')
  })
  const PORT = 3000
  server.listen(PORT, () => {
    console.log('The server is listening at port: ', PORT)
  })
  
  Visual Studio Code
  code-server
  
  
  
  ```
