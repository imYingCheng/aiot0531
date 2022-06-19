# AIoT Github

## Lecture 15: IoT Flask Web (deploy to heroku)

### step 1 : Clone this github  

* 創建一個資料夾'aiot0531'，  
<img src="https://user-images.githubusercontent.com/94978161/174471764-a033c33c-fc1f-48a1-bede-d73d7025f6b6.png">  

* 並在終端機輸入以下程式碼clone老師的檔案到'aiot0531'，  
```python
git clone https://github.com/huanchen1107/aiot0530-start-no-token
```

* 完成後將資料夾中的.git刪除，方便建立新的git repository。  
<img src="https://user-images.githubusercontent.com/94978161/174472510-e6767dda-2a92-491d-bce2-60acfaf8703c.png">

### step 2 : install some package  

* 輸入以下程式碼以安裝所需套件  
```python
pip install gunicorn Flask==2.0.1 Jinja2==3.0.1 psycopg2 sklearn pandas numpy
```

### step 3: add an heroku postgredb

* 註冊一個heroku的帳號
* 新增一個App(aiot0531hw)
* 新增外掛功能heroku postgred
<img src="https://user-images.githubusercontent.com/94978161/174473233-5f20b2f1-b689-4190-9c0e-466a3d4209a0.png">

### step 4: login to heroku pstgredb using HeidiSQL

#### 取得資料庫資料
* 點選data  
<img src="https://user-images.githubusercontent.com/94978161/174473547-f2578c4e-5e26-48c1-938b-46685cc646ee.png">

* 選擇本App  
<img src="https://user-images.githubusercontent.com/94978161/174473619-830f8a5f-ffc5-447c-b65b-2b39f37df9b4.png">

* 選擇setting>>Database Credentials>>view credentials  
<img src="https://user-images.githubusercontent.com/94978161/174473893-adb26e54-649c-44e9-9538-6ab06d91e8b3.png">
  
#### 使用 HeidiSQL 連線至 postgres DB
* 下載HeidiSQL
* 輸入Database Credentials中的資訊
<img src="https://user-images.githubusercontent.com/94978161/174474414-86990a3d-eb96-4c18-ade1-2189517fc274.png">

### step 5: import postgredb (in db/postgre.db)
* 在public資料庫匯入`./db/postgres.sql`
<img src="https://user-images.githubusercontent.com/94978161/174475482-f5b6ac00-11b6-48ee-af0a-7c99777a4955.png">

* 

### step 6: setting db in app.py


```sql
myserver ="<fill-in-Heroku-Postgredb-DB-sever>"
myuser="<fill-in-Heroku-Postgredb-DB-user>"
mypassword="<fill-in-Heroku-Postgredb-DB-pwd>"
mydb="<fill-in-Heroku-Postgredb-DB-db>"

```
### step 7: testing locally by running python app.py

### step 8: deploy to github (new private github repositoy)

delete .git and git remote add origin master github.com/xxxxx


### step 9: Heroku deploy from github

### step 10: Complete

Sample link 1:
https://awinlab-aiot.herokuapp.com/

Sample link 2: 
https://aiot0529.herokuapp.com/





