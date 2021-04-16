
# Security Concept
```
資訊安全目標_機密性C、完整性I與可用性A
(CIA triad) == confidentiality, integrity and availability 

CEH
```
##
```
下列何者是「機密性confidentiality」的正確意涵？
(A) 確保被使用的為正確資料，未遭人竄改   (B) 確保網路通訊中的參與者，不會拒絕承認他們的行為
(C) 確保資訊服務隨時可被取用            (D) 防止未經授權的人或系統存取資料或訊息
```
D

##
```
下列何者是「完整性integrity」的正確意涵？
(A) 確保被使用的為正確資料，未遭人竄改   (B) 確保網路通訊中的參與者，不會拒絕承認他們的行為
(C) 確保資訊服務隨時可被取用            (D) 防止未經授權的人或系統存取資料或訊息
```
A

## 
```
請問「確保已授權之使用者可適時、可靠的存取資料與資源」所代表的意義是下列何者？
(A) 機密性  (B) 完整性   (C) 可用性    (D) 可讀性
```
 (C)
##
```
學生侵入學校的伺服器，偷偷竄改自己的期末考成績。這是破壞了資訊的哪一項特性？
(A) 保密性（Confidentiality） (B) 完整性（Integrity）
(C) 可用性（Availability）  (D) 責任性（Accountability）
```
(B)

## 
```
組織對外服務之官方網站遭受駭客透過DDoS攻擊，請問此為下列哪項遭受破壞？
(A) 機密性  (B) 完整性  (C) 可用性  (D) 可讀性
```
(C)
##
```
組織內部某資料庫遭受駭客藉由惡意程式入侵，竊走大量個人資料，請問此為下列哪些特性遭受破壞？
(A) 可用性  (B) 機密性   (C) 完整性  (D) 可讀性
```
(B)

## 
```
下列哪種攻擊可以用來繞過實體(Physical)和邏輯(Logical)主機安全機制?
(A) 暴力攻擊(Brute-Force Attack)
(B) 阻斷服務攻擊(Denial-of-Service Attack)
(C) 社交工程(Social Engineering)
(D) 通訊埠掃描(Port Scan)
```
(C)
##
```
下列何者非社交工程攻擊方式？ 
(A)  利用電子郵件誘騙使用者登入偽裝之網站以騙取帳號及通行碼 
(B)  利用程式設計缺陷，向程式寫入錯誤的內容 
(C)  利用即時通訊軟體如 LINE，偽裝親友來訊，誘騙點選來訊中之連結後中毒 
(D)  利用電話佯裝資訊人員，騙取帳號及通行碼
```
B
##
```
短時間內傳送大量的封包給另一部電腦的攻擊方式，稱之為？ 
(A) 木馬程式或殭屍病毒(backdoor]botnet) (B) 釣魚郵件攻擊(Phishing) 
(C) 阻斷服務攻擊(DDos) (D) 中間人攻擊(MiTM)
```
C

## 
```
當作業系統安裝好之後，為了避免因為安全因素導致作業系統遭受駭客入侵，應採取下列何項措施較佳？ 
(A) 更新病毒碼 (B) 更新修補程式 (C) 更新防火牆設定 (D) 更新入侵偵測系統 
```
B
##
```
下列何者不是微軟 Windows 作業系統中，具特權權限之帳號？ 
(A) Administrator (B) root 
(C) 在 Administrators 群組中之一般使用者帳號 (D) Local System 
```
B

## 
```
請問下列何者「並非」作業系統中毒的可能徵狀?
(A) 檔案無故遭加密
(B) 上網速度變慢或無法連線
(C) 無故出現對話框,且無法關閉
(D) 資料讀取速度變快
```
D

12

# crypto
```
底下為Caesar cipher(密碼)的加密問題
若設定為rot=3
ie. a->d, b->e ..... x->a, y->b,z->c
請問 xzap 是明文時,加密後的密文是 
(A)xzap   (B)acds  (C)uwxm  (D) kmnc

請問 xzap 是密文時,解密後的明文是
(A)xzap   (B)acds  (C)uwxm  (D) kmnc
```

# python 基本語法

## 
```
試問以下程式執行後輸出什麼結果:
#!/usr/bin/python3
a = {"name" : "Eric", "age" : 90}
print(type(a))

(A) str   (B) dict   (C) list   (D) tuple
```
(B)
## 
```
試問以下程式執行後輸出什麼結果:
#!/usr/bin/python3
thisislist = [1,2,3,4,5]
print(type(thisislist))

(A) str   (B) dict   (C) list   (D) tuple
```
(C)

## 
```
試問以下程式執行後輸出什麼結果:
#!/usr/bin/python3
word = "arttarataaa"
print(type(word))

(A) str  (B) dict   (C) list   (D) tuple
```
(A)

##
```
thisislist = [1,2,3,4,5]
print(thisislist[-4])
以上程式碼輸出的結果是？
(A) 1  (B) 2  (C) 3  (D) 4
```
(B) 


##
```
thisislist = [1,2,3,4,5]
print(thisislist[_________])
若要以上程式碼輸出的結果是2,3,4需要填入什麼？
(A) 1:4   (B) 1:3   (C) 1-4   (D) 1-3
```

( A )

## 
```
print("3*2*(17-2)")會印出甚麼結果:
(A)0   (B)90  (C)出現錯誤,無法印出  (D)3*2*(17-2)
```
```
print(3*2*(17-2))會印出甚麼結果:
(A)0   (B)90  (C)出現錯誤,無法印出  (D)3*2*(17-2)
```
```
print("abc""+""def")會印出甚麼結果:
(A)出現錯誤,無法印出   (B)abc+def  (C)abc""+""def  (D)abcdef
```
```
print("abc"+"def")會印出甚麼結果:
(A)出現錯誤,無法印出   (B)abc+def  (C)abc""+""def  (D)abcdef
```
```
底下程式執行後結果為何?
word = "arttarataaa"
print(word.replace("a", "z",3))
(A)出現錯誤,無法印出   (B)arttarataaa  (C)zrttzrztaaa (D)zrttzrztzzz
```
```
底下程式執行後結果為何?
word = "arttarataaa"
print(word.replace("a", "z"))
(A)出現錯誤,無法印出   (B)arttarataaa  (C)zrttzrztaaa (D)zrttzrztzzz
```

##
```
thisisdict1 = dict(a="1", b="2", c=3)
thisisdict1.pop(“b”)
print(thisisdict1)
以上程式碼輸出的結果是？

(A) {'a': '1', 'c': 3}   (B) {'a': '1', 'b': '2', 'c': 3}   
(C) ['a': '1', 'c': 3]   (D) ['a': '1', 'b': '2', 'c': 3]
```
(A)

##
```
if 0:
    print("Hello")
以上程式碼輸出的結果是？
(A) 沒有任何輸出  (B) 語法錯誤  (C) Hello  (D) False
```
(A)
##
```
if 100 == “100”:
    print("Hello")
以上程式碼輸出的結果是？
(A) 沒有任何輸出  (B) 語法錯誤  (C) Hello  (D) False
```
(A)



##
```
i = 10
while i < 15:
  i += 1
  if i >= 13:
    continue
  print(i)
以上程式碼輸出的結果是？

(A) 15  (B) 13、14  (C) 10、11   (D) 11、12
```
( D )

##
```
def add(a,b):
  return a+b

print(_______)
若要計算50+100以上程式碼需填入什麼？

(A) add(50,100)  (B) add(50+100)  (C) add(150)   (D) add()
```
(A)
##
```
def func(n):
  return lambda a : a * n

a = func(5)
print(a(10))
以上程式碼輸出的結果是？

(A) 100  (B) 50   (C) 150   (D) 25
```
 (B)
## 
```

```

## 
```

```
## 
```

```
## 
```

```




5

## Python 基本應用:  數字系統轉換 Number System Conversion
```
https://byjus.com/maths/number-system/#:~:text=A%20number%20system%20is%20defined,algebraic%20structure%20of%20the%20figures.
```
```
完成底下填空選擇題:

程式如下
bin_n = 0b1011111111

print("0b1011111111 二進位的數字可被轉換成:")
print("十進位(Decimal)的表達:" , bin_n)
print("八進位(octal)的表達:",oct(bin_n))
print("十六進位(hexadecimal)的表達:",hex(bin_n))

執行結果如下:
0b1011111111 二進位的數字可被轉換成:
十進位(Decimal)的表達: 767
八進位(octal)的表達: 0o1377
十六進位(hexadecimal)的表達: 0x2ff
```
```
完成底下填空選擇題:

程式如下
bin_n = 0b1011111111

print("0b1011111111 二進位的數字可被轉換成:")
print("十進位(Decimal)的表達:" ,_[填空 A] ___)
print("八進位(octal)的表達:",_[填空B] ___)
print("十六進位(hexadecimal)的表達:",_[填空 C] ___)

執行結果如下:
0b1011111111 二進位的數字可被轉換成:
十進位(Decimal)的表達: 767
八進位(octal)的表達: 0o1377
十六進位(hexadecimal)的表達: 0x2ff
```

```
[填空 A] === (A)bin_n (B) oct(bin_n) (C)dec(bin_n)  (D) hex(bin_n)

[填空 B] === (A)bin_n (B) oct(bin_n) (C)dec(bin_n)  (D) hex(bin_n) 
                
[填空 C] === (A)bin_n (B) oct(bin_n) (C)dec(bin_n)  (D) hex(bin_n) 
```
## Python and CTF
```
#!/usr/bin/python

c = '66 114 101 97 107 65 76 76 67 84 70 123 65 109 118'

flag = ""

for x in c.split(' '):
  flag += chr(int(x))

print(flag)
```
```
#!/usr/bin/python

c = '66 114 101 97 107 65 76 76 67 84 70 123 65 109 118'

flag = ""

for x in _[填空 A] ___:
  flag += __[填空 B] __

print(flag)
```
```
1. [填空 A] === (A)c.split(' ')  (B) c.separate(' ') 
                (C) c.sep(' ')  (D) c.s(' ') 
2. [填空 B] ===  (A)int(chr(x)) (B)chr(int(x)) 
                 (C)int(ch(x))  (B)ch(int(x)) 
```
## 
```




```

##
```


```


## 
```


```

##
```


```


## 
```


```
