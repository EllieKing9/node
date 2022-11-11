# node.js

■ History
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
```

■ Deveploment Environment
- online code editor : glitch (https://glitch.com/)
  ```
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
  ```
  
- Visual Studio Code
  code-server (https://github.com/coder/code-server)
  
  1. work on WSL
  ```
  $sudo apt-get update
  $sudo apt-get install wget ca-certificates
  
  $sudo curl -fsSL https://code-server.dev/install.sh | sh
  //curl -fsSL https://code-server.dev/install.sh | sh -s -- --dry-run
  
  or manually //파일을 직접 다운로드(download release file)
  $sudo mkdir /mnt/blank
  $sudo curl -fOL https://github.com/coder/code-server/releases/download/v4.5.2/code-server_4.5.2_amd64.deb
  $sudo dpkg -i code-server_4.5.2_amd64.deb
  //$sudo reboot
  $code-server //최초 실행시 .config 파일 생성(first excute : Wrote default config file to ~/.config/code-server/config.yaml)
  ctrl + z
  $nano ~/.config/code-server/config.yaml
    bind-addr: [ip]:[port]  ex)127.0.0.1:8080
    auth: [password]/[none]
    password: [..q.sd....]
    cert: [true]/[false]/[path, *.pem]
    cert-key: [path, *key.pem]
  
  // Ubuntu 실행 시 자동으로 code-server가 수행 되도록 할려면 서비스 등록을 해준다.
  $sudo systemctl enable --now code-server
  //sudo systemctl enable --now code-server@$USER
  ! WSL에서는 systemctl 를 지원하지 않는다 //systemctl(x) -> service(o)
  $sudo systemctl start code-server //실행
  $sudo systemctl stop code-server //중지
  $sudo systemctl restart code-server //재시작
  $sudo systemctl status code-server 
  ```
  2. work on Oracle Cloud (https://github.com/EllieKing9/OCI_code-server)
  ```
    ↗↗↗
  ```
  
  
  
■ Node.js (https://nodejs.org/ko/download/)
- NVM (https://github.com/nvm-sh/nvm)
  ```
  nvm를 통해서 node를 버젼별로 설치하고 관리할 수 있다.
  node version management !!가 매우 중요 하며
  ```
  
  1. Install on WSL (https://docs.microsoft.com/ko-kr/windows/dev-environment/javascript/nodejs-on-wsl)
  ```
  $curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
  or 
  $wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    
  $nvm ls
  $nvm ls-remote --lts
       > https 접속이 안됨? (회사 방화벽)
  ```
  
  2. Install on Oracle Cloud
  ```
  
  ```
  
- tj/n (https://github.com/tj/n)
  ```
  설치?
  
  $n
    설치된 버전 리스트 확인 > 버전 선택 > 선택한 버전의 node로 환경 자동으로 세팅됨
  $node --version // 버전 확인
  $n latest // 가장 최신 버전의 node 설치
  $echo SN_PREFIX // node가 설치된 (상위)경로 표시 ex)~/n/n/versions/node/12.18.3 ..
  
  
  
  ```
  
■ NPM(Node Pakage Management)

node가 설치되면 npm(node package manager)이 같이 설치된다.

- with VScode & terminal
  package.json 만들기
  ```
  $npm init -y //package.json 자동 생성
    "scripts": {
      "test": "echo \"Hello, world!\""
    }
  $npm run test
  ```
  
  main.js 만들기
  ```
  
  ```
  
  Formatting: Prettier
  ```
  $npm install --save-dev prettier // 설치
  // node_modules 폴더 생성
  // package-lock.json 생성
  // package.json 에 의존성 생성
      "devDependencies": {
        "prettier": "^2.2.1" 
      }
      
  
  ```
  
  Linting
  ```
  ```
