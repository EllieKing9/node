# node
<h5>

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
  https://github.com/coder/code-server
  
  > work on WSL
  $sudo apt-get update
  $sudo apt-get install wget ca-certificates
  
  $sudo curl -fsSL https://code-server.dev/install.sh | sh
  //curl -fsSL https://code-server.dev/install.sh | sh -s -- --dry-run
  or manually
  $sudo mkdir /mnt/blank
  파일을 직접 다운로드(download release file)
  $sudo curl -fOL https://github.com/coder/code-server/releases/download/v4.5.2/code-server_4.5.2_amd64.deb
  $sudo dpkg -i code-server_4.5.2_amd64.deb
  reboot
  $code-server //최초 실행시 .config 파일 생성(first excute : Wrote default config file to ~/.config/code-server/config.yaml)
  ctrl + z
  $nano ~/.config/code-server/config.yaml
  bind-addr: [ip]:[port]  ex)127.0.0.1:8080
  auth: [password]/[none]
  password: [..q.sd....]
  cert: [true]/[false]
  
  Ubuntu 실행 시 자동으로 code-server가 수행 되도록 할려면
  서비스 등록을 해준다.
  $sudo systemctl enable --now code-server
  //sudo systemctl enable --now code-server@$USER
  
  $sudo systemctl start code-server //실행
  $sudo systemctl stop code-server //중지
  $sudo systemctl restart code-server //재시작
  $sudo systemctl status code-server 
  
  use NginX => https://hakawati.co.kr/445
  
  ```
