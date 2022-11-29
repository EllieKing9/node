
■ RESTful API
  ```
  const http = require('http')
  
  const server = http.createServer((req, res_ => {
    res.statusCode = 200
    res.end('Hello!')
  })
  
  const PORT = 4000
  
  server.isten(PORT, () => {
    console.log(`The server is listening at port: ${PORT}`)
  })
  
  ```

httpie.io (https://httpie.io/)
  ```
  http 테스트 툴
  $sudo apt-get install httpie
  $http localhost:4000
  ```

nodemon

jsdoc.app
