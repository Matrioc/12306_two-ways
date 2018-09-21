#### 第一种抢票，需要安装python环境，新手不推荐：
#### 设计思路
![image](https://github.com/herrywen-nanj/12306_two-ways/blob/master/resources/images/%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)

```
这个利用谷歌插件
chromedriver的安装方法：

1、查看chrome版本号：帮助->关于Google Chrome，在打开的设置页面中间可以看到Chrome的当前版本，例如：当前Chrome版本63，下载v2.34版本的chromedriver
2、下载chromedrive驱动：https://chromedriver.storage.googleapis.com/index.html
3、注意浏览器chrome与chromedriver的对应版本（我的chrome是63+，因此选择2.34的chromedriver）
4、参照下方的对应关系表下载
```


```
chromedriver版本  支持的Chrome版本
    v2.34           v61-63
    v2.33           v60-62
    v2.32           v59-61
    v2.31           v58-60
    v2.30           v58-60
    v2.29           v56-58
    v2.28           v55-57
    v2.27           v54-56
    v2.26           v53-55
    v2.25           v53-55
    v2.24           v52-54
    v2.23           v51-53
    v2.22           v49-52
    v2.21           v46-50
    v2.20           v43-48
    v2.19           v43-47
    v2.18           v43-46
    v2.17           v42-43
    v2.13           v42-45
    v2.15           v40-43
    v2.14           v39-42
    v2.13           v38-41
    v2.12           v36-40
    v2.11           v36-40
    v2.10           v33-36
    v2.9            v31-34
    v2.8            v30-33
    v2.7            v30-33
    v2.6            v29-32
    v2.5            v29-32
    v2.4            v29-32
下载好插件之后，就去将chromedriver放在chrome安装目录下，即C:\Program Files (x86)\Google\Chrome\Application
利用谷歌插件chromedriver进行登录抢票，现已经放在D盘了，直接填写config.ini，然后运行hack12306程序即可。
```

#### Config文件说明
```
最简单的方法是修改 config.ini， 然后填写自己的乘车信息， 这些配置都可以在运行期间进行修改。
; config.ini
; 配置信息：请依照注释修改必选项，非必选项可以删除等号后的值

## 登陆账号和密码
[login]
### username：12306登录用户名，必选参数
username=xxx@qq.com
### password：12306登录密码，必选参数
password=xxx

## cookie信息，出发站，目的站
[cookieInfo]
### starts：对应搜索框出发地，必选参数，请输入中文名称，例如：武汉
starts=武汉
### ends：对应搜索框目的地，必选参数，请输入中文名称，例如：南京
ends=南京
### dtime：对应搜索框出发日，必选参数，时间格式：年-月-日，例如 2018-01-19
## 时间格式2018-01-19
dtime=2018-01-11

## order：车次，选择第几趟，0则从上至下依次点击，必选参数，如果要特定车次，需要先找到车次在列表中的次序，有效值如下：
#### 0->从上至下点击
#### 1->第一个车次
#### 2->第二个车次
[orderItem]
order=2

## users：乘客姓名，必选参数，中文姓名，支持多个乘客，用英文逗号隔开，例如：张三,李四
### 乘客姓名需要提前加入到登录的12306账号的联系人中，为了程序自动选择乘客姓名
[userInfo]
users = xxx

## 车次类型：
[trainInfo]
### train_types：车次类型，可选参数，默认全部车次，支持多个值，用英文逗号隔开，特别需求的在此指定值，不指定请删除等号后的值，默认是车次不勾选，有效值如下：
#### T->特快
#### G->高铁
#### D->动车
#### Z->直达
#### K->快车
train_types = D,G

### start_time：发车时间，可选参数，不指定请删除等号后的值，默认值“00:00--24:00”
### 时间格式 12:00--18:00，有效值如下：
##### 00:00--24:00->00:00--24:00
##### 00:00--06:00->00:00--06:00
##### 06:00--12:00->06:00--12:00
##### 12:00--18:00->12:00--18:00
##### 18:00--24:00->18:00--24:00
start_time = 12:00--18:00

[confirmInfo]
## 席别
### seat_type：席别，可选参数，不指定请删除等号后的值，默认按照12306预定到的车次的席别，有效值如下：
#### 硬座
#### 硬卧
#### 软卧
#### 一等软座
#### 二等软座
#### 商务座
#### 一等座
#### 二等座
#### 混编硬座
#### 特等座
seat_type = 二等座

## 网址，必选参数
## 此部分不需改动
[urlInfo]
ticket_url = https://kyfw.12306.cn/otn/leftTicket/init
login_url = https://kyfw.12306.cn/otn/login/init
initmy_url = https://kyfw.12306.cn/otn/index/initMy12306
buy = https://kyfw.12306.cn/otn/confirmPassenger/initDc

## 路径信息
[pathInfo]
### driver_name: 浏览器名称，必选参数
driver_name = chrome
### executable_path: 浏览器驱动路径，必选参数
### windows路径例如：C:\Users\sanshunfeng\Downloads\chromedriver.exe
executable_path = C:\Users\sanshunfeng\Downloads\chromedriver.exe
```

```
指定config文件运行程序：python hack12306.py -c /Users/xxx/config.ini
```


### 第二种抢票方法：
```
直接解压缩下面的12306抢票软件.rar。找到.exe运行就可以了
```
