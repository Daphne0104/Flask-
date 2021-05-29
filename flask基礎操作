from flask import Flask , render_template,request #展示html文件
                             
import datetime
app = Flask(__name__)

   #路由解析，通過用戶訪問的路徑，匹配相應的函數
#@app.route('/')
#def hello_world():
  #  return 'Hello 你好123!'

        #主程序
if __name__ == '__main__':
    app.run(debug=True)  #

#要開啟debug模式，才會顯示錯誤+及時改正


#透過訪問路徑，獲取用戶的字符串參數
@app.route('/user/<name>')     #http://127.0.0.1:5000/user/lin
def welcome(name):
    return f'Hello 你好{name}!'

#透過訪問路徑，獲取用戶的整數參數 ...還有float類型
@app.route('/user/<int:id>')
def welcome2(id):
    return f'Hello 你好{id}!'

#路由路徑不能重複，用戶通過唯一路徑訪問特定的函數

# flask由2個模塊組成  W負責路由+函數定義 j負責函數內容

#返回給用戶渲染後的文件
# @app.route('/')     #定義路徑
# def test():
#     return render_template("test.html") #把網頁轉給用戶
#

#向頁面傳遞一個變量
@app.route('/')     #定義路徑
def test2():
    time = datetime.date.today()   #普通變量
    name = ["小張","小汪","小趙"]  #列表類型
    task = {"任務":"打掃","時間":"3小時"}  #字典類型
    return render_template("test.html",var = time,list=name,task = task)       #變量名隨意

#表單提交
@app.route('/test/register')   #內容路徑
def  register():
    return render_template("test/register.html")   #template下的文件結構

#接收表單提交的路由，需要指定method為post
@app.route('/result',methods=["POST","GET"])    #method預設為get
def result():
    if request.method=="POST":
        result = request.form       #資料統一，傳回字典
        return render_template("test/result.html",result = result) #左邊是送到jinja2的參數，右邊是內容，這內容來自於路由參數
