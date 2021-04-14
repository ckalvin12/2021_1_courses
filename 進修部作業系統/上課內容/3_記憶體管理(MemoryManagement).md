# 3_記憶體管理(MemoryManagement)
```
記憶體管理の主記憶體管理
[42]: 記憶體階層(Memory Hierarchy)及Locality principle
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
