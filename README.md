
# v2ray 部署在 openshift 、Arukas等
openshift: 内存设置为256M，每 project 可配置 4 Pods。

Docker 镜像：crownzhu/v2ray:latest

环境变量： CONFIG_JSON（配置）、CERT_PEM（证书）、KEY_PEM（私钥）

用notepad++将上述变量中 \r\n 替换为\\n，变成一行，导入容器。

客户端： android Actinium、windows v2ray 可用同一个服务端。



{
  "log": {
    "loglevel": "warning"
  },
  "inbound": {
    "protocol": "vmess",
    "port": 8080,
    "settings": {
      "clients": [
        {
          "id": "6936eeda-f303-4cc6-965b-fea4433938af",
          "alterId": 64,
          "security": "chacha20-ploy1305"
        }
      ]
    },
    "streamSettings": {
      "network": "ws"
    }
  },
  "inboundDetour": [],
  "outbound": {
    "protocol": "freedom",
   "settings": {}
  }
}
