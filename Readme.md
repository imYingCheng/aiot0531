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
* 在public資料庫匯入`./db/postgres.sql`，並按下執行按鈕。
<img src="https://user-images.githubusercontent.com/94978161/174475482-f5b6ac00-11b6-48ee-af0a-7c99777a4955.png">

* 即可看到Sensor資料表
<img src="https://user-images.githubusercontent.com/94978161/174477942-4c55a8e4-63c9-4aae-ade6-98d0e55a8764.png">

### step 6: setting db in app.py
* 根據上面`Data Credentials`的資訊修改程式

```sql
myserver ="ec2-52-204-195-41.compute-1.amazonaws.com"
myuser="zolrsjlkwszwfs"
mypassword=略
mydb="dakhchn3f4ccsl"

```
<img src="https://user-images.githubusercontent.com/94978161/174478332-ae4c69a8-644a-4b88-9a0e-99e6a63e148d.png">

### step 7: testing locally by running python app.py
#### 測試
* 在終端機輸入以下程式碼來測試app.py的運行結果
```python
python app.py
```
<img src="https://user-images.githubusercontent.com/94978161/174478694-5b8a738e-5d5d-4765-9f28-2e2fac39ccaf.png">

#### 測試結果
* noAI成功
<img src="https://user-images.githubusercontent.com/94978161/174479660-098efd51-2791-4e6f-b00d-aab5384e8c95.png">

* Call AI成功
<img src="https://user-images.githubusercontent.com/94978161/174479630-0099d7af-c0ec-4f3b-b165-eb95a8e976eb.png">

### step 8: deploy to github (new private github repositoy)
* 在step1的時已經先將原本的`.git`刪除，並重新建立了`public github repository`，所以直接使用目前的github repository即可。  

### step 9: Heroku deploy from github
* 到`Heroku`點選剛剛新增的App(`aiot0531hw`)
* 按下`deploy`，再按下面的`Github`
* 輸入要連結的repository名稱(`aiot0531`)，再按下`connect`
<img src="https://user-images.githubusercontent.com/94978161/174479975-cb132b48-2c24-4ed0-bf83-07ab2c6b498a.png">

* 按下`Enable Automatic Deploys`和`Deploy Branch`
<img src="https://user-images.githubusercontent.com/94978161/174480295-ede816ca-0f07-4f11-b4f6-bd7fad9efe5e.png">

* `deploy`成功
<img src="https://user-images.githubusercontent.com/94978161/174480339-ee8882e2-594e-4828-991a-71c5b25bf757.png">

### step 10: Complete

Sample link : https://aiot0531hw.herokuapp.com/  





