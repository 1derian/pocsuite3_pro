# POCSUITE3个人修改版

## 介绍

基于原版pocsuite3的简单修改 , 实现fofa高级会员满血调用 , 支持poc检测结果保存到本地文件 

更方便大家批量检测和后期利用 

**新增功能**

```
1.新增fofa查询条数限制参数 --max-size  , 默认10000 (自动去重可能只有8000+)
   注 : 只有高级fofa会员才可以使用
2.新增--save-file 字段 , 默认不开启 , 可以指定存在漏洞的targets保存到你想要保存的文件中,方便后期利用
3.修改了默认线程个数20
4.新增 xxl-job 弱口令 poc
5.新增 apollo 弱口令 poc
6.新增 canal 弱口令 poc
7.新增 cve-2022-26134 poc
8.部分源码添加了注释 , 方便参考 等等

欢迎有兴趣的师傅一起交流
```

## 安装

环境

```
python3 >= 3.7
windows/linux
```

如果你之前安装过pocsuite3 请先卸载原版的pocsuite3

```
pip3 uninstall pocsuite3
```

下载该项目

```
git clone https://github.com/1derian/pocsuite3_pro.git
cd pocsuite3_pro
pip3 install -r requirements.txt

```

## 使用

直接使用fofa语句 , 批量检测 cve-2022-26134 , 并将结果保存到 res.txt

```
python3 cli.py -r ./pocs/cve-2022-26134.py  --dork-fofa app="ATLASSIAN-Confluence"  --max-size 500 --save-file ./Confluence_res.txt --threads 30
```

![image](https://user-images.githubusercontent.com/64243067/172038969-c0363f87-5d12-4486-8b81-b4c918613b3b.png)

![image-20220605142632884](https://picgo-1301783483.cos.ap-nanjing.myqcloud.com/image/image-20220605142632884.png)

注 : 

```
第一次使用fofa语句 , 会提示输入账号和key
```

## 参考

https://github.com/knownsec/pocsuite3

## 免责声明🧐

本工具仅面向合法授权的企业安全建设行为，如您需要测试本工具的可用性，请自行搭建测试环境。

在使用本工具进行检测时，您应确保该行为符合当地的法律法规，并且已经取得了足够的授权。请勿对非授权目标进行扫描。

如您在使用本工具的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。