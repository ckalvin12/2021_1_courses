# Windows Server實戰主題
```
A單一Windows Server伺服器管理
B.各種伺服器架設與管理 + 安全性強化
C.Windows Server雲端技術

D.大型windows環境建置 ==> Windows 網域

E.使用Powershell管理Windows Server環境
```
# A單一Windows Server伺服器管理
```
Chapter 1｜Windows Server 2019 概觀
Chapter 2｜安裝 Windows Server 2019
Chapter 3｜Windows Server 2019 基本環境

Chapter 4｜本機使用者與群組帳戶
Chapter 7｜檔案權限與共用資料夾

Chapter 9｜群組原則與安全設定 ==> 本機電腦
    9-4 本機安全性原則 security settings
     gpedit.msc==> 本機電腦 原則==>安全性設定
     帳戶原則-密碼原則
     帳戶原則-帳戶鎖定原則
     本機原則－稽核政策(audit Policy)
     本機原則－使用者權限指派(User Rights Managements)[超多]
     本機原則－安全性選項(security options)
     
    9-6 稽核資源的使用
    gpedit.msc ==> 設定各種觸發的條件
    eventviewer ==> 檢視觸發的事件
    
    稽核登入事件
    稽核檔案存取行為
    稽核印表機的存取行為


Chapter 10｜磁碟系統的管理   ==>想想看linux怎麼做
   10-1 磁碟概觀
   UEFI模式
   檢視磁碟分割區 – 使用Diskpart
   格式化為NTFS、ReFS、exFAT、FAT32或FAT


   10-2 基本磁碟區的管理
   壓縮磁碟區
   磁碟初始化
   建立主要磁碟分割區
      MBR基本磁碟：最多可有4個主要磁碟分割區
      GTP基本磁碟：最多可有128個主要磁碟分割區
   建立延伸磁碟分割區
      一個基本磁碟內只可以建立一個延伸磁碟分割區
      利用Diskpart建立延伸磁碟分割區
   建立邏輯磁碟機 
   指定「使用中」的磁碟分割區
   磁碟分割區的格式化、加標籤、轉換檔案系統與刪除
   延伸基本磁碟區
   
   10-3 動態磁碟的管理
     簡單磁碟區(simple volume)
     跨距磁碟區(spanned volume)
     等量磁碟區(striped volume)
     鏡像磁碟區(mirrored volume)
     RAID-5磁碟區(RAID-5 volume)

   10-4 搬移磁碟
   


Chapter 12｜系統啟動的疑難排除
```
```
Windows Server 2019 Administration Fundamentals
Dauti, Bekim
Packt Publishing  2019-10-11
```
# B.各種伺服器架設與管理 + 安全性強化
```
Windows Server 2019 系統與網站建置實務

File and Storage Services

Chapter 8｜架設列印伺服器 ==> Printer server
Chapter 13｜利用 DHCP 自動指派 IP 位址 ==> DHCP server
Chapter 14｜解析 DNS 主機名稱 ==> DNS server

Chapter 15｜架設 IIS 網站 ==> web server

安裝 網頁伺服器(IIS) 
網頁儲存地點的設定
   預設:%SystemDrive%\inetpub\wwwroot (主目錄)
   主目錄可變更為
         本機電腦的其他資料夾
         其他電腦的共用資料夾：指定使用者帳戶名稱與密碼
   預設的首頁檔案
   Default Web Site的首頁檔
   新增default.htm檔案
   HTTP重新導向 == 設定
   實體目錄與虛擬目錄
     實體目錄實例演練
     虛擬目錄實例演練
   建立多個網站
   IIS網站的安全性設定
    驗證使用者的名稱與密碼
    驗證方法
        匿名驗證：不需要輸入使用者名稱與密碼(使用群組帳號IUSR)
        基本驗證：需使用者名稱與密碼，但並沒有被加密
        摘要式驗證：IIS電腦必須加入AD DS網域、需AD DS使用者
        Windows驗證：使用者名稱與密碼會經過雜湊處理後再傳送
        預設只啟用匿名驗證方式，其他3種需另外安裝
    驗證方法的設定
         可針對單一檔案、資料夾或網站來設定
         選用順序：匿名驗證、Windows驗證、摘要式驗證、基本驗證
    透過IP位址來限制連線
    透過NTFS 或ReFS權限來增加安全性
    遠端管理IIS網站與功能委派
       lab:IIS網頁伺服器的遠端管理設定
    安裝「管理服務」與建立「IIS管理員使用者」帳戶
Chapter 16｜PKI 與 https 網站 ==> https 

Chapter 11｜分散式檔案系統
```

# C.Windows Server雲端技術
```
Windows Server 2019 系統與網站建置實務

Chapter 5｜建置虛擬環境 ==> Hyper-V
Chapter 17｜Server Core、Nano Server 與 Container
```

# D.大型windows環境建置 ==> Windows 網域
```
Windows Server 2019 Active Directory 建置實務

第1章 Active Directory網域服務(AD DS)
第2章 建立AD DS網域
第3章 網域使用者與群組帳戶的管理

第4章 利用群組原則管理使用者工作環境
第5章 利用群組原則部署軟體
第6章 限制軟體的執行

第7章 建立網域樹狀目錄與樹系
第8章 管理網域與樹系信任
第9章 AD DS資料庫的複寫
第10章 操作主機的管理
第11章 AD DS的維護
第12章 將資源發佈到AD DS
第13章 自動信任根CA
第14章 利用 WSUS 部署更新程式
附錄A AD DS與防火牆
附錄B Server Core伺服器的管理
```

# E.使用Powershell管理Windows Server環境
```
Windows Server 2019 Automation with Powershell Cookbook - Third Edition
Lee, Thomas   Packt Publishing   2019-02-28

學習要點
Perform key admin tasks on Windows Server 2019
Employing best practices for writing PowerShell scripts and configuring Windows Server 2019
Use the .NET Framework to achieve administrative scripting
Set up VMs, websites, and shared files on Azure
Report system performance using built-in cmdlets and WMI to obtain single measurements


學習主題 ===>
Establishing a PowerShell Administrative Environment

Managing Windows Networking
Managing Windows Active Directory
Managing WIndows Storage
Managing Shared Data
Managing Windows Update
Managing Printers
Leveraging Containers
Managing WIndows Internet Information Server
Managing Desired State Configuration
Managing Hyper-V
Managing Azure
Managing Performance and Usage
Troubleshooting WIndows Server
Know the tools you can use to diagnose and resolve issues with Windows Server
```
