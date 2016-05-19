##此檔案將說明做出一個分頁或主頁時所要調整的部分  
###簡單流程圖:
![Alt text](https://github.com/kangfizz/Read.md-edit-Toturial/blob/master/Pic1.png "pic1")  
  
  
###詳細說明:  
####1.	(templates)xxxx.html  
先在templates資料夾中寫好一個’xxxx.html’的程式,  
注意,如果要從view.py中拿變數的話,變數將要如此取得: {{變數名}}  
####2.	View.py:  
  在你的app裡(此預設為trips)  
  舉個例子:(使用render來接收)  
  from django.shortcuts import render  
  
def hello_world(request):  
    return render(request, 'xxxx.html', {  
        'current_time': datetime.now(),  
    })  
		  另外一個重點是.在這個PYTHON檔裡面可以寫PYTHON然後將變數傳入你request的html網址中。  
  
  
####3.	url.py:  
 	在你的mysite裡  
		a.先設定從trips中取出你設定的def :   
		from trips.views import hello_world  
		b.在urlpatterns = []中放入你要設定的url與def  
			(後面記得加”,”)  
	url(r'^hello/$', hello_world),  
	這樣就設定了127.0.0.1:8000/hello/  
