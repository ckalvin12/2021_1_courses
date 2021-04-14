# 儲存體管理(Mass-storage management)
```
儲存體架構(Mass-Storage Structure ):

HDD Scheduling ==> 作業系統の磁碟排程(Disk Scheduling)演算法
[1]先到先做(FCFS)
[2]最短搜尋時間優先(Shortest Seek Time First：SSTF)
[3]掃瞄法(Scan或Elevator Algorithm)
[4]循環掃瞄法Circular SCAN
[5]Look
[6]C-Look


作業系統の磁碟管理
磁碟格式化/啟動區塊(boot) /Defragment(重組磁碟)/
壞損區塊(Bad blocks)處理機制
  Sector Sparing(磁區備份)/Sector forwarding(磁區轉換)
Sector slipping(磁區順延)

[69]:RAID:（Redundant Arrays of Inexpensive Disks）
[70]:Storage Area Networks (SAN )與NAS

Chapter 11 Mass-Storage Structure

11.3 NVM Scheduling 497
11.4 Error Detection and Correction 498
11.5 Storage Device Management 499
11.6 Swap-Space Management 503
11.7 Storage Attachment 505
11.8 RAID Structure 509
```
## I/O Systems I/O管理  
```
I/O Hardware硬體觀點 ==> addressing/傳輸方式[see Vol 1.計算機硬體篇] 

軟體觀點 ==> Application I/O Interface(應用程式介面):Device Driver(驅動程式)

作業系統觀點 ==>Kernel I/O Subsystem(系統核心的IO 子系統):
      改善I/O效能的方法:
        ①I/O排程(I/O Scheduling)
      利用某儲存空間:(1)Buffering(緩衝) (2)Cache(快取) (3)Spooling
      Error Handling(錯誤處理)
      Kernel Data Structure

I/O的運作:Transform I/O request to Hardware Operation
STREAMS
Performance(IO 效能)
```
