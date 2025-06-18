# NewAPI 一键创建APIKEY项目

一个简单的单页面应用，一键获取 [NewAPI](https://github.com/QuantumNous/new-api) 的API KEY，免去复杂注册兑换流程。

## 功能特性

- 一键获取API Key
- 易于部署
![image](https://github.com/user-attachments/assets/551e55d6-f84f-4b9e-9ca2-fb7f191f83c3)

## 部署步骤

1. **修改配置文件**
   - 打开`api-init.html`文件
   - 查找并替换所有`https://xxx.com`为你的NewAPI服务地址（域名或IP+端口）

2. **上传文件**
   - 将修改后的`api-init.html`上传到服务器指定目录，例如：`/etc/nginx/static/`

3. **配置Nginx**
   ```nginx
   # 拦截 /init 并返回静态页面
   location = /init {
       default_type text/html;
       alias /etc/nginx/static/api-init.html;  # 替换为实际上传目录
   }
   ```
   - 配置完成后刷新配置:sudo nginx -t && sudo nginx -s reload
      
## 访问
	- https://你的域名/init
