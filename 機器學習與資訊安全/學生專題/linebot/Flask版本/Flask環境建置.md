#
```
https://blog.techbridge.cc/2017/06/03/python-web-flask101-tutorial-introduction-and-environment-setup/
```
```
# 顯示目前虛擬環境列表
$ conda info -e 
# 創建虛擬環境
$ conda create -n 套件名稱 python=3.6
# 進入虛擬環境（若是 Windows cmder 環境不用加 source） ，成功後提示字元變成：（套件名稱）$
$ source activate 套件名稱
# 離開虛擬環境（若是 Windows cmder 環境不用加 source） 
$ source deactivate
```
```
建立虛擬環境

$ conda create -n python-flask-todo-app python=3.6
$ source activate python-flask-todo-app
安裝 Flask 模組

$ pip install flask
```
```
通常開發專案時我們會將已安裝模組名稱和版本號存成一個列表，以便下次安裝使用：
$ pip freeze > requirements.txt


根據 requirements.txt 列表安裝模組：
$ pip install -r requirements.txt
```
