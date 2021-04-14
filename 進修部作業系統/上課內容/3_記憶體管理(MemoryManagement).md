# 3_記憶體管理(MemoryManagement)
```
記憶體階層(Memory Hierarchy)及Locality principle
主記憶體管理(Main-Memory Management)
虛擬記憶體管理(virtual-Memory Management)
```
## 主記憶體管理(Main-Memory Management)
```

記憶體階層(Memory Hierarchy)及Locality principle


記憶體管理の主記憶體管理
[43]:主記憶體管理(Main-Memory Management): 基本觀念
Logical address(邏輯位址) vs Physical address(實體位址)、位址轉換
記憶體保護(Memory Protection)::目的與作法
   硬體保護機制:(1)界限暫存器(Bound/limit Registers)                 
                  (2)重定位暫存器(relocation/base register)
解決記憶體容量限制的:overlays(重疊) 與 Swap(置換)

[44]:主記憶體管理:記憶體配置(Memory Allocation):
      連續配置法 vs非連續配置

[45]:主記憶體管理:連續記憶體配置(Memory Allocation)法
       單一分割配置 vs多重分割配置: 
1.固定多重分割  2.可變多重分割:
	 最先適合法(First-fit)/最佳適合法(Best-fit)/最不適合法(Worst-fit)
	 
[46]:記憶體配置(Memory Allocation)之斷裂問題(Fragmentation problem):  
外部斷裂(Internal Fragmentation)/內部斷裂(External Fragmentation)
    緊湊法(Compaction)    

[47]:主記憶體管理:非連續記憶體配置(Memory Allocation)法
    [1] 分頁法Paging  [2] 分段法Segmentation  
    [3]分頁式分段Segmentation With paging
[48]:分頁(Paging)原理
[49]:分頁法之硬體加速篇：
       位址查閱緩衝(Translation Look-aside Buffer, TLB)
[50]:解決分頁表太大的問題
      分頁表(Page Table)之結構(structure)：
     [1]多層次分頁(Multi-level/Hierarchical paging)
     [2]雜湊分頁表(Hashed page tables)
```
## 虛擬記憶體管理(virtual-Memory Management)
```

[53]: 虛擬記憶體(virtual-Memory Management)基本觀念與管理技術
     ✔需求分頁(demand paging)/需求分段(demand segmentation)[略]

[54]: Page fault（分頁錯誤）與處理流程

[55]:需求分頁(demand paging)之Page Replacement分頁替換演算法   
[1]先進先出演算法(FIFO, First In-First Out)
[2]最佳演算法(Optimal algorithm)
[3]最久未用演算法(LRU algorithm, Least Recently Used)
[4]最久未用近似演算法(LRU approximation algorithm)
4a.額外參考位元演算法(Additional-reference-bit algorithm)
4b.二次機會演算法(second-chance algorithm)
4c.加強版二次機會演算法(enhanced second-chance algorithm)
[5]計數為基礎的演算法(Counting-based algorithm)
 5a.最不常用演算法(The least frequently used page-replacement algorithm, LFU)
5b.最常用演算法(The most frequently used page-replacement algorithm, MFU)
[6]分頁緩衝演算法(Page-buffer algorithm)
Belady anomaly(反常)


[56]: Thrsahing(輾轉現象)與解決方案: 
1.Work Set Model    
2.Page fault frequency
```
