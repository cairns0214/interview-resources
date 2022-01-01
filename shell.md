<!-- TOC -->

- [常见工具](#常见工具)
  - [tcpdump](#tcpdump)
    - [常用选项](#常用选项)
    - [过滤表达类](#过滤表达类)

<!-- /TOC -->

# 常见工具
## tcpdump
### 常用选项
| 选项 | 示例 | 说明 |
| ---- | ---- | ---- |
| -i | tcpdump -i eth0 | 指定网络借口，默认是0号接口，any表示所有接口 |
| -nn | tcpdump -nn | 不解析ip地址和端口号的名称 |
| -c | tcpdump -c 5 | 限制要抓取的网络包个数 |
| -w | tcpdump -w file.pcap | 保存到文件中，文件名通常以.pcap为后缀 |
### 过滤表达类
| 选项 | 示例 | 说明 |
| ---- | ---- | ---- |
| host、src host、dst host | tcpdump -nn host 192.168.1.100 | 主机过滤 |
| port、src port、dst port | tcpdump -nn port 80 | 端口过滤 |
| ip、ip6、arp、tcp、udp、icmp | tcpdump -nn tcp | 协议过滤 |
| and、or、not | tcpdump -nn host 192.168.1.100 and port 80 | 逻辑表达式 |
| tcp[tcpflags] | tcpdump -nn "tcp[tcpflags] & tcp-syn != 0" | 特定状态的tcp包 |