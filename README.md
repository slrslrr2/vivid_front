## Project nginx setup

- Local
 - nginx

```
http {
  include       mime.types;
  default_type  application/octet-stream;

  sendfile        on;
  keepalive_timeout  65;

	upstream vivid-backend  {
		server localhost:7776;
	}
  
  server {
    listen 80;
    server_name vivid.co;

    location / {
          proxy_set_header X-Real-IP            $remote_addr;
          proxy_set_header X-Forwarded-Host     $host;
          proxy_set_header X-Forwarded-Server   $host;
          proxy_set_header X-Forwarded-For      $proxy_add_x_forwarded_for;
          proxy_set_header Host                 $http_host;
          proxy_set_header X-SSL-Server         true;
          proxy_pass   http://vivid-backend;
    }

    # location ~* \.(gif|jpg|png|js|css|bmp|swf|xml|ico|html|woff|otf|eot|ttf|svg)$ {
    #     root /Dev;
    # }
  }
}
```

  - etc/hosts
```
  127.0.0.1 vivid.co
```



## Project setup
```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```
