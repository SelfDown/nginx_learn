# nginx_learn
nginx 学习
  location /static/libs/{
           # add_header Cache-Control no-store;
            root $old_static_parent;
            access_log off; 
            proxy_set_header X-Request-Id $request_id;
            add_header X-Request-Id $request_id;
             expires  30d;
           add_header ‘Access-Control-Max-Age’ 0;
            break;
           
        }
        
        
 1 静态文件缓存设置  add_header ‘Access-Control-Max-Age’ 0; 文件从浏览器直接 获取，不经过服务器。from disk cache
 
 
  gzip_min_length 1k;  
    gzip_http_version 1.1;
    gzip_comp_level 9; 压缩级别，越大越高
    gzip_types text/plain application/json application/x-javascript application/css application/xml application/xml+rss text/javascript application/x-httpd-php image/jpeg image/gif image/png image/x-ms-bmp application/javascript;压缩类型
    gzip_vary on;
 
