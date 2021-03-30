# 
```


```
#
```
Linux 檔案系統架構
```

# Linux 檔案系統架構
```

```

#
```
https://blog.techbridge.cc/2017/12/23/linux-commnd-line-tutorial/

ls：list，查看檔案及子目錄

列出基本資料夾資料 ==>  ls
列出詳細資料和隱藏資料
 // -l 列出詳細資料 -a 列出隱藏資料
 $ ls -la
列出部分檔案：

 // 列出為 .js 的檔案
 $ ls *.js
 
 
pwd：print work directory，印出目前工作目錄

cd：change directory，移動進入資料夾

移動到目前資料夾下的 examples 資料夾：
 $ cd ./examples
 
移動到家目錄：~：

移動到上一層目錄 ..： ==>  $ cd ..
移動到根目錄 /：==>  $ cd /

mkdir：make directory，創建新資料夾

 $ mkdir examples
 
cp：copy，複製檔案

先將字串 TEST 存入 README.md 文件中

 $ echo "TEST" > README.md
 $ cp README.md
mv：move (rename) files，移動檔案或是重新命名檔案

移動檔案：

 $ mv README.md /examples/README.md
重新命名

 $ mv README.md README_MV.md
rm：remove file，刪除檔案

 $ rm README.md
刪除目前資料夾下副檔名為 .js 檔案：

 $ rm *.js
刪除資料夾和所有檔案：

 $ rm -f examples
touch：用來更新已存在文件的 timestamp 時間戳記或是新增空白檔案

 $ touch README.md
cat：將文件印出在終端機上

 $ cat README.md
tail：顯示檔案最後幾行內容

$ tail README.md
持續顯示更新內容，常用於 web server 看 log debug 使用：

$ tail -f README.md
more：將檔案一頁頁印在終端機上

可以使用上下移動換頁，按 q 離開：

$ more README.md
file：檢查檔案類型

$ file README.md
// README.md: HTML document text, UTF-8 Unicode text 
```
