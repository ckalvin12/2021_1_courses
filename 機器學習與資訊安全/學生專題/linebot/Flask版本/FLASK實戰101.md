# anaconda 環境下python執行
```
最好建虛擬環境
https://blog.techbridge.cc/2017/06/03/python-web-flask101-tutorial-introduction-and-environment-setup/

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
anaconda 環境已安裝flask

啟動anaconda prompt
切換到你的flask程式目錄夾
執行python XXX.py
```
# server.py
```
from flask import Flask
app = Flask(__name__)

@app.route('/')
def index():
    return '歡迎來到首頁!'

@app.route('/hello')
def hello():
    return '歡迎來到歡迎頁面!'

if __name__ == '__main__':
    app.run()
```
```
執行伺服器程式 ==> python server.py

打開瀏覽器 127.0.0.1:5000
```

# 
```
from flask import Flask
app = Flask(__name__)

@app.route('/')
@app.route('/index')
def index():
    return '這是本網站首頁!'

if __name__ == '__main__':
    app.run()
```
#
```
from flask import Flask
app = Flask(__name__)

@app.route('/hello/<string:name>')
def hello(name):
    return '{}，歡迎來到 Flask!'.format(name)

if __name__ == '__main__':
    app.run()
```
#
```
from flask import Flask
from flask import request
app = Flask(__name__)

@app.route('/', methods=['get'])
def index():
    name = request.args.get('name')
    return "Hello, {}".format(name)

if __name__ == '__main__':
    app.run(debug=True)
```
# post.py
```
from flask import Flask
from flask import request
app = Flask(__name__)

@app.route('/', methods=['GET','POST'])
def submit():
    if request.method == "POST":
        username = request.values['username']
        password = request.values['password']
        if username=='david' and password=='1234':
            return '歡迎光臨本網站！'
        else:
            return '帳號或密碼錯誤！'
    return """
            <form method='post' action=''>
                <p>帳號：<input type='text' name='username' /></p>
                <p>密碼：<input type='text' name='password' /></p>
                <p><button type='submit'>確定</button></p>
            </form>
    """

if __name__ == '__main__':
    app.run()
```

```
(base) E:\Dragon\flask\ch02>python post.py
 * Serving Flask app "post" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [18/Mar/2021 11:48:18] "[37mGET / HTTP/1.1[0m" 200 -
127.0.0.1 - - [18/Mar/2021 11:52:14] "[37mPOST / HTTP/1.1[0m" 200 -
127.0.0.1 - - [18/Mar/2021 11:52:16] "[37mGET / HTTP/1.1[0m" 200 -
127.0.0.1 - - [18/Mar/2021 11:52:21] "[37mPOST / HTTP/1.1[0m" 200 -
```
```
打開瀏覽器127.0.0.1:500 
```
# template1.py
```
from flask import Flask
app = Flask(__name__)

from flask import render_template
@app.route('/hello')
def hello():
    return render_template('hello.html')

if __name__ == '__main__':
    app.run()
```
### hello.html ===> 檔案放在template目錄夾
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title>第一個模版</title>
</head>
<body>
	<h1> Flask 網站 </h1>
    <h2> 歡迎光臨！ </h2>
    <h4> 2019年11月12日 </h4>
</body>
</html>
```

#
```
from flask import Flask
app = Flask(__name__)

from flask import render_template
from datetime import datetime
@app.route('/hello/<string:name>')
def hello(name):
    now = datetime.now()
    return render_template('hello2.html', **locals())

if __name__ == '__main__':
    app.run()
```
```
from flask import Flask
app = Flask(__name__)

from flask import render_template
from datetime import datetime
@app.route('/hello/<string:name>')
def hello(name):
    now = datetime.now()
    return render_template('hello3.html', **locals())

if __name__ == '__main__':
    app.run()
```
```
from flask import Flask
app = Flask(__name__)

from flask import render_template
@app.route('/variable')
def variable():
    student = {'學號':'874523', '姓名':'張三', '性別':'男'}
    fruit = ['蘋果', '香蕉', '芭樂', '百香果']
    return render_template('variable.html', **locals())

if __name__ == '__main__':
    app.run()
```
```
from flask import Flask
app = Flask(__name__)

from flask import render_template
@app.route('/show')
def show():
    person1={"name":"Amy","phone":"049-1234567","age":20}
    person2={"name":"Jack","phone":"02-4455666","age":25}
    person3={"name":"Nacy","phone":"04-9876543","age":17}
    persons=[person1,person2,person3]
    return render_template('show.html', **locals())

if __name__ == '__main__':
    app.run()
```
### templates\hello.html
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title>第一個模版</title>
</head>
<body>
	<h1> Flask 網站 </h1>
    <h2> 歡迎光臨！ </h2>
    <h4> 2019年11月12日 </h4>
</body>
</html>
```
### templates\hello2.html
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title>傳送參數模版</title>
</head>
<body>
	<h1> Flask 網站 </h1>
    <h2> {{name}}，歡迎光臨！ </h2>
    <h4> 現在時刻：{{now}} </h4>
</body>
</html>
```
### templates\hello3.html
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title>使用靜態檔案模版</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style1.css') }}">
</head>
<body>
	<h1> Flask 網站 
	    <img src="{{ url_for('static', filename='ball.png') }}" width="32" height="32" />
	</h1>
    <h2> {{name}}，歡迎光臨！ </h2>
    <h4> 現在時刻：{{now}} </h4>
</body>
</html>
```
### templates\variable.html
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title>第一個模版</title>
</head>
<body>
    <h4>姓名：{{student.姓名}}</h4>
    <h4>最喜歡的水果：{{fruit.1}}</h4>
</body>
</html>
```
### templates\show.html
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title>基本資料</title>
</head>
<body>
    <h3>   
    {% for person in persons%}
       <ul>
           <li>姓名：{{person.name}}</li>
           <li>手機：{{person.phone}}</li>
           <li>年齡：{{person.age}}</li>
       </ul>
    {% endfor %}  
    </h3>
</body>
</html>
```
### static\style1.css
```
h4 {
    color:red;
}
```
