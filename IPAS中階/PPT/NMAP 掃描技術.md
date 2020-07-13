#
```
Which of the following will perform an Xmas scan using NMAP?
A. nmap -sA 192.168.1.254
B. nmap -sP 192.168.1.254
C. nmap -sX 192.168.1.254
D. nmap -sV 192.168.1.254
```

c

```
NMAP -sn 192.168.11.200-215
The NMAP command above performs which of the following?
A. A ping scan
B. A trace sweep
C. An operating system detect
D. A port scan
```
Answer: A


```
Which Nmap option would you use if you were not concerned about being detected and
wanted to perform a very fast scan?
A. -T0
B. -T5
C. -O
D. -A
```

Answer: B

# NMAP 掃描技術
```
http://n.sfs.tw/content/index/10505

XMAS TREE SCAN [-sX]
  說明：將TCP所有flag打開(FIN, URG, PUSH, ACK, SYN)
  結果：unix會把往Open port的封包丟棄，
        Win2000回應不正常

NULL SCAN [-sN]
  說明：將TCP所有flag關閉，RFC793未定義如何處理此類封包
  結果：除了BSD開啟埠會丟棄外，
        其餘系統回應RST，可由此判斷是否為BSD系統
```

```
Inverse Scan-聖誕節XMAS掃描!
https://ithelp.ithome.com.tw/articles/10222572

NMAP 掃描方式說明
http://n.sfs.tw/content/index/10505
```
