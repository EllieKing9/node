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
  //$sudo curl -fsSL https://code-server.dev/install.sh | sh -s -- --dry-run
  
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
  //$wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    
  $nvm ls
  $nvm ls-remote --lts
       > https 접속이 안됨? (회사 방화벽)
  ```
  
  2. Install on Oracle Cloud
  ```
  
  ```
  
- tj/n (https://github.com/tj/n)
  ```
  // 설치
  $sudo mkdir /mnt/install
  $cd /mnt/install
  $sudo curl -L https://raw.githubusercontent.com/tj/n/master/bin/n -o n
  $sudo bash n lts
    installing : node-v18.12.1
         mkdir : /usr/local/n/versions/node/18.12.1
         fetch : https://nodejs.org/dist/v18.12.1/node-v18.12.1-linux-x64.tar.xz
       copying : node/18.12.1
     installed : v18.12.1 (with npm 8.19.2)
  // now node and npm are available
  $sudo npm install -g n
    npm notice New major version of npm available! 8.19.2 -> 9.1.1
    npm notice Changelog: https://github.com/npm/cli/releases/tag/v9.1.1
    npm notice Run npm install -g npm@9.1.1 to update!
  $n
    설치된 버젼 리스트 확인 및 > 버젼 선택 > 선택한 버젼의 node로 환경 자동으로 세팅됨
  $node --version // 버젼 확인
  $n latest // 가장 최신 버젼의 node 설치
  $n version // 해당 버젼의 node 설치
  $n rm version // 해당 (cached)버젼의 node 삭제
  // ? $echo SN_PREFIX // node가 설치된 (상위)경로 표시 ex)~/n/n/versions/node/12.18.3 ..
  
  ```
  
■ NPM(Node Pakage Management) 

node가 설치되면 npm(node package manager)이 같이 설치된다.

- package.json 만들기(with VScode & terminal)
  ```
  $npm init -y
    + package.json 자동 생성됨
    "scripts": {
      "test": "echo \"Hello, world!\""
    }
  $npm run test
  ```
  
  main.js 만들기
  ```
  
  ```
  
  Node.js and JavaScript in Visual Studio Code (https://code.visualstudio.com/learn/educators/nodejs)
  
  1. Formatting (Prettier)
  ```
  // Prettier 설치
  $npm install --save-dev prettier
    + node_modules 폴더 생성됨
      |_bin
      |_prettier
    + package-lock.json 생성됨
    + package.json 에 의존성 추가됨
      "devDependencies": {
        "prettier": "^2.2.1" 
      }
      
  // Prettier 사용
  prettier-Code formatter 패키지 설치 (VS Code)
    // 아래 설정 폴더 및 생성 자동 생성 확인?
    
    > .prettierrc 파일 생성 (VS Code)
    {
      "semi": false,
      "singleQuote": true
    }
  
    > .vscode 폴더 생성
      |_ settings.json 파일 생성
        {
          "[javascript]": {
           "editor.formatOnSave": true,
           "editor.defaultFormatter": "esbenp.prettier-vscode"
          }
        }
  ```
  
  2. Linting (ESLint)
  ```
  //eslint 패키지 설치 (VS Code)
    // 아래 설정 폴더 및 생성 자동 생성 확인?
    
  // ESLint 설치
  $npm install --save-dev eslint
    + package.json 에 의존성 추가됨
      "devDependencies": {
      "eslint": "^7.24.0",
      ..
    }  
    package-lock.json 에 의존성 추가됨
  
  // Airbnb JavaScript Style Guide 설치
  $npm install --save-dev eslint-config-airbnb-base eslint-plugin-import 
    + package.json 에 의존성 추가됨
      "devDependencies": {
        "eslint-config-airbnb-base": "^14.2.1",
        "eslint-plugin-import": "^2.22.1",
        ..
      }  
     
  // eslconfig prettier 설치 // 기존 prettier와 충돌 방지
  $npm install --save-dev esl-config-prettier
  
  // eslint node plugin 설치
  $npm install --save-dev eslint-plugin-node
  
  // 사용 설정
    > .eslintrc.js 파일 생성 (VS Code)
      module.exports = { // Allow 작업 필요
        extends: ['airbnb-base', 'plugin:node/recommended', 'prettier'], //'prettier' 맨 뒤!로
      }
  
  // main.js 에서 사용
  /* eslint-disable-next-line no-console */
  console.log(eval())
  ```
  
  3. Type Checking (TypeScript)
  ```
  // TypeScript 설치
  $npm install --save-dev typescript
    + package.json 에 의존성 추가됨
      "devDependencies": {
        "typescript": "^4.2.4",
        ..
      } 
     
  // main.js 에서 사용
  > @ts-check
  
  // node 에서 사용되는 Type checking 설치
  $npm install --save-dev @types/node
  
  // main.js 에서 사용
    ..
  
  ```

  TypeScript와 jsconfig.json //JavaScript에서 TypeScript의 type checking 기능만 사용
  ```
    > jsconfig.json 파일 생성 (VS Code)
    {
      "compilerOptions": {
        "strict": true
      },
      "include": [
        "src/**/*"
      ]
      //..
    }
    
  ```
