---
title: hexo+github搭建个人网站
---
## 引
今天又看到一个hexo+github的个人网站，勾起了自己搭一个的兴趣，于是就。。。

## 下载hexo

1.本地新建文件夹 myblog （名称随意）。

2.进入文件夹，打开cmd命令窗口 （可以直接在文件夹路径处输入cmd）


```
//第一条   这是安装hexo的基础框架
npm install -g hexo

//第二条   这是初始化hexo框架 这个可能会比较慢
hexo init

//第三条 安装所需要的组件
npm install

//第四条 编译生成静态页面
hexo g

//第五条 启动本地服务
hexo s
```

## 创建个人仓库

github上创建一个和你用户名相同的仓库，后面加.github.io，也就是 xxx.github.io

## 部署上git

1.修改_config.yml,YourgithubName就是你的GitHub账户
```
deploy:
  type: git
  repo: https://github.com/YourgithubName/YourgithubName.github.io.git
  branch: master
```
2.安装deploy-git ，也就是部署的命令,这样你才能用命令部署到GitHub。
`npm install hexo-deployer-git --save`
然后
```
hexo clean
hexo generate
hexo deploy
```
其中 hexo clean清除了你之前生成的东西，也可以不加。
hexo generate 顾名思义，生成静态文章，可以用 hexo g缩写
hexo deploy 部署文章，可以用hexo d缩写
注意deploy时可能要你输入username和password。

## 切换next主题

下载主题(之后可以直接在文件下git pull更新)
`git clone https://github.com/theme-next/hexo-theme-next themes/next`
修改_config.yml, `theme: next`
修改next里的配置文件，
```
#scheme: Muse
#scheme: Mist
#scheme: Pisces
scheme: Gemini
```

## hexo相关操作api
官网地址：[https://hexo.io/zh-cn/docs/writing](https://hexo.io/zh-cn/docs/writing)