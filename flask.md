
![image](https://github.com/wonima136/xiu/assets/100024933/b82f05c4-43d9-4099-86c1-fee6c54792d2)
![image](https://github.com/wonima136/xiu/assets/100024933/3a4d3871-d4a4-4fea-ab6e-2631e01d0de7)
![image](https://github.com/wonima136/xiu/assets/100024933/2a23e788-7567-40cf-93c9-b473305a606a)
![image](https://github.com/wonima136/xiu/assets/100024933/bc68b849-a272-497e-bd1a-b8c486edcebc)
![image](https://github.com/wonima136/xiu/assets/100024933/a65f871d-3f96-4b49-8bd0-06510d55655f)
![image](https://github.com/wonima136/xiu/assets/100024933/22357eba-6743-4ad7-8ad3-e92aa0030d2d)
![image](https://github.com/wonima136/xiu/assets/100024933/d9c6d645-320c-41c0-8329-efa50d0023cd)
![image](https://github.com/wonima136/xiu/assets/100024933/438e3b85-a642-497e-a810-d1ecae02da9e)
![image](https://github.com/wonima136/xiu/assets/100024933/51d5c92d-6337-47eb-a381-ab1a6ee24246)
![image](https://github.com/wonima136/xiu/assets/100024933/3bf24a0a-1aec-4fca-b828-a4fd61889d5b)
![image](https://github.com/wonima136/xiu/assets/100024933/e4706ff9-e191-497a-9147-79c8017a47ed)
![image](https://github.com/wonima136/xiu/assets/100024933/09c35f9a-75aa-48b4-8408-033c3c0cb1bc)
![image](https://github.com/wonima136/xiu/assets/100024933/0332aeec-1327-4f7c-a9cb-b95742d1ea14)
![image](https://github.com/wonima136/xiu/assets/100024933/c5da7a28-d9bc-4645-8cb0-ac1d20a0ca83)

```conf
# 替换端口：6033
# 确保,cloudflare_ips_v4.txt，googlebot_ips.txt,whitelist_ips.txt,路径正确.
# deny all;如果前面没有井号就是开启限制阻拦
# error_page 403 https://jp.linel.top/diy/flask+wp/; 当开启阻拦后403状态跳转到的落地页地址
# access_log 确保路径存在,路径中使用了 $host 变量一个域名生成一个单独log文件
# # 网站在解析顶级的情况下  www跳转到顶级域名，注意这里要修改证书的路径
----------------------------------------------------
location / {
        include uwsgi_params;
        uwsgi_pass 127.0.0.1:6033;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header REMOTE-HOST $remote_addr;
        add_header X-Cache $upstream_cache_status;
        proxy_set_header X-Host $host:$server_port;
        proxy_set_header X-Scheme $scheme;
        proxy_connect_timeout 30s;
        proxy_read_timeout 86400s;
        proxy_send_timeout 30s;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
		include /www/googlebot_ips/cloudflare_ips_v4.txt;  # 包括 Cloudflare IP
		real_ip_header CF-Connecting-IP;
		include /www/googlebot_ips/googlebot_ips.txt;
         include /www/googlebot_ips/whitelist_ips.txt;
         # deny all;
         # 网站403状态跳转
		#error_page 403 https://jp.linel.top/diy/flask+wp/;
    }
    # HTTP反向代理相关配置结束 <<<

    access_log  /www/wwwlogs/tongji/2024-05-11/$host.log;
}
##################################################################
```
![image](https://github.com/wonima136/xiu/assets/100024933/70e1b911-06e3-4a44-8248-27913fd56503)
![image](https://github.com/wonima136/xiu/assets/100024933/f1dcb736-0b22-49ed-b06e-7a566685a79d)
```nginx
找到
buffer-size = 
替换成
buffer-size = 65535
# 服务器状态，重启就OK了
```
