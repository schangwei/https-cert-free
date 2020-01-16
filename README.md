# https-cert-free
免费的HTTPS证书申请认证和下载

### 准备工作（配置NS记录）
* 一个域名 ， 假设是要为 test.antiycloud.com 申请证书
* 多个域名，以空格分隔，例如: *.test.antiycloud.com test.antiycloud.com
* 需要配置 _acme-challenge.test.antiycloud.com 的NS记录为 **txt-verify.antiy.net.cn** 

### 准备好以上的工作 ， 就可以正式开始证书的申请工作了
### 本篇以 www.sslforfree.com 申请免费证书为例


* 填写需要申请的域名，如有多个请以空格分开，这里是假设为 test.antiycloud.com 申请证书
![](https://github.com/schangwei/https-cert-free/blob/master/01.png)


* 选择手动认证DNS服务
![](https://github.com/schangwei/https-cert-free/blob/master/02.png)

* 获取需要设置的TXT记录的值
* 在这里是 1Hm1nO367PZ0BPybo_yKEVLudK2q9d4LnyGqrP6_Ex0

## 设置TXT值
访问设置URL:

http://txt-verify.antiy.net.cn/set-txt?key=[password]&txt=1Hm1nO367PZ0BPybo_yKEVLudK2q9d4LnyGqrP6_Ex0

设置成功会返回 set ok

其中参数的 password 请联系管理员（长伟同学）获取 ， txt 为刚才在 sslforfree 网页中获取的值

## 检查是否已经可以申请https证书
返回申请证书的界面，点击: **Verify _acme-challenge.test.antiycloud.com** 检查。

注意：一般由于 TTL 的原因解析不能立即生效，请等待解析生效。
检查成功会返回如下结果：

`TXT Record(s) Found. Make sure the value matches the value specified by the instruction for with the domain hostname: `

`HOST: _acme-challenge.test.antiycloud.com`
`WARNING - TTL is not 1 Second. Change the TTL to 1 second. Contact your DNS provider if unsure. If you cannot set the TTL to 1 second you must wait the TTL before the the records will get updated. For example if the TTL is set to 300 you must wait 300 seconds before the records will change to be able to verify. If you update the TTL now you will have to wait the previous TTL until the new TTL shows up.`

`TTL: 5`

`TXT: 1Hm1nO367PZ0BPybo_yKEVLudK2q9d4LnyGqrP6_Ex0`


## 下载证书
点击下载证书，然后就可以将证书配置到你的服务器上了


### 以下网站可以免费申请https证书：
* https://getfreessl.net
* https://gethttpsforfree.com
* https://www.sslforfree.com
