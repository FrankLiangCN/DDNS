#企业微信
1. 下载企业微信 → 左上角三横杠 → 全新创建企业 → 个人组件团队(创建个人的企业群聊)
2. 进入群聊添加 [群机器人] 复制机器人Webhook地址填入ddns-go后台Webhook URL地址栏
3. 在RequestBody栏填入回调函数，格式：
```
{ "msgtype": "markdown","markdown": { "content": "公网IP变更： \n - IPv4地址：#{ipv4Addr} \n - 域名更新结果：#{ipv4Result} \n - IPv6地址：#{ipv6Addr}\n - 域名更新结果：#{ipv6Result} \n" }}
```
