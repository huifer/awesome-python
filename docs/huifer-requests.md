# python requests
- Author: [HuiFer](https://github.com/huifer)
- Description: 本文介绍requests简单实用
## 官网
- https://github.com/psf/requests
- https://requests.readthedocs.io/en/master/
> Requests is an elegant and simple HTTP library for Python, built with ♥.
> - 使用requests可以模拟浏览器的请求
>


## 安装
```
pip install requests
```

## 导入
```py
import requests
```
## 请求
### 基本操作
- response = request.get()
- response.text 查看响应内容
- response.url 查看完整url
- response.encoding 查看响应头编码
- response.status_code 查看响应码
- response.content 查看响应数据(字节流)


### get
- requests.get("url") 发送get请求
- requests.get(url=url,params=params) 发送 get 请求携带参数 params 参数为dict类型
- requests.get(url=url,params=params,headers=headers) headers 头部信息
### post
- request.post(url,data=query_data) 发生 post 请求,参数为 query_data 类型为 dict


### proxies 代理
```py
proxies = {
    "http":"",
    "https":""
}
res  = request.get(url,proxies=proxies)
```
- request.get(url,proxies=proxies) 发送一个代理请求


### auth
- requests.get('https://api.github.com/user', auth=('user', 'pass')) 登录验证(用户名,密码)

### cookies
- cookies = response.cookies 获取cookies
- cookies_dict = requests.utils.dict_from_cookiejar(cookies) 将cookies转换为dict


### session
```python
# 创建session对象
s = requests.Session()
# session访问
s.get('https://httpbin.org/cookies/set/sessioncookie/123456789')
r = s.get('https://httpbin.org/cookies')
print(r.text)
```

### SSL
- response = requests.get(url, verify=True) verify 参数为是否进行ssl校验


### 发送文件
```python
file_dict = {
    'f1': open('readme.md', 'rb')
}
requests.request(method='POST',
                 url='http://127.0.0.1:8000/test/',
                 files=file_dict)

```
