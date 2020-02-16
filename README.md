Removed
本生成器仅供研究试验目的，不支持也不推荐用于大量用户/端口的场合
设置
服务1: 服务种类

VMess设置
用户设置
用户uuid（重新生成）
a7e4c658-9020-8516-60eb-e39992b91ae5
使用的alterID数量（越大越不容易被识别，但消耗越大）
91
端口设置
端口号(1 ~ 65535)
8889

是否是动态端口（可能减少流量管控限制，也可能更快被封）

是否是mKCP协议（可能更快，也可能彻底被封或不稳定）
传输配置
传输层加密(TLS)

启用传输层加密
服务端配置
 {
    "log": {
        "access": "/var/log/v2ray/access.log",
        "error": "/var/log/v2ray/error.log",
        "loglevel": "warning"
    },
    "inbound": {
        "port": 8889,
        "protocol": "vmess",
        "settings": {
            "clients": [
                {
                    "id": "a7e4c658-9020-8516-60eb-e39992b91ae5",
                    "level": 1,
                    "alterId": 91
                }
            ]
        },
        "streamSettings": {
            "network": "kcp"
        }
    },
    "outbound": {
        "protocol": "freedom",
        "settings": {}
    },
    "inboundDetour": [],
    "outboundDetour": [
        {
            "protocol": "blackhole",
            "settings": {},
            "tag": "blocked"
        }
    ],
    "routing": {
        "strategy": "rules",
        "settings": {
            "rules": [
                {
                    "type": "field",
                    "ip": [
                        "0.0.0.0/8",
                        "10.0.0.0/8",
                        "100.64.0.0/10",
                        "127.0.0.0/8",
                        "169.254.0.0/16",
                        "172.16.0.0/12",
                        "192.0.0.0/24",
                        "192.0.2.0/24",
                        "192.168.0.0/16",
                        "198.18.0.0/15",
                        "198.51.100.0/24",
                        "203.0.113.0/24",
                        "::1/128",
                        "fc00::/7",
                        "fe80::/10"
                    ],
                    "outboundTag": "blocked"
                }
            ]
        }
    }
} 
客户端配置
输入服务端地址
输入本地端口号（建议大于1024）
选择服务

选择用户

选择服务端端口


是否使用Mux.cool在一个底层连接上传输多个连接（测试特性）
