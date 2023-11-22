# DDNS

## 一键DDNS（基于[ddns-go][ddns-go])

自动判断CPU架构，并下载最新版本二进制文件

### 一键脚本命令：

```
wget -qO- https://raw.githubusercontent.com/FrankLiangCN/DDNS/main/ddns.sh | bash
```

安装完成后请打开 http://IP:9876 端口进行配置


# Webhook

<details>

<summary>企业微信</summary>

1. 下载企业微信 → 左上角三横杠 → 全新创建企业 → 个人组件团队(创建个人的企业群聊)
2. 进入群聊添加 [群机器人] 复制机器人Webhook地址填入ddns-go后台Webhook URL地址栏
3. 在RequestBody栏填入回调函数，格式：

```
{ "msgtype": "markdown","markdown": { "content": "公网IP变更： \n - IPv4地址：#{ipv4Addr} \n - 域名更新结果：#{ipv4Result} \n - IPv6地址：#{ipv6Addr}\n - 域名更新结果：#{ipv6Result} \n" }}
```

</details>

<details>

<summary>Telegram</summary>

一个用于接收 [ddns-go][ddns-go] 通知的 Telegram 机器人

## 使用
1. 打开并启用 [@DDNSGoBot][DDNSGoBot]
2. 发送 /gethook 命令
3. 复制 Webhook URL 并粘贴
4. 复制 RequestBody 并粘贴
注：未启用 IPv4 或 IPv6 可删除对应 Object

```
{
    "ipv4": {
        "result": "#{ipv4Result}",
        "addr": "#{ipv4Addr}",
        "domains": "#{ipv4Domains}"
    },
    "ipv6": {
        "result": "#{ipv6Result}",
        "addr": "#{ipv6Addr}",
        "domains": "#{ipv6Domains}"
    }
}
```
感谢
[@WingLim][telegram-bot]

</details>

[ddns-go]: https://github.com/jeessy2/ddns-go
[DDNSGoBot]: https://t.me/DDNSGoBot
[telegram-bot]: https://github.com/WingLim/ddns-telegram-bot
