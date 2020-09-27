#### 简介

使用cf works 反代多个IBM账号，适用于多个IBM账号用户（没啥大用，本着不浪费原则）



#### 使用说明

~~~
# 一键代码
# 特殊说明：中间需要自己生成UUID，提示有生成UUID的网址，自行打开，务必记住，UUID生成一次就行，多个账户使用一个UUID
wget --no-check-certificate -O install.sh https://raw.githubusercontent.com/w2r/IBM_multi_account/master/1.sh && chmod +x install.sh  && ./install.sh

~~~

CF works反代代码：

使用说明，几个账户就就修改**第四行**的数字，然后修改case数目，几个账户就几个case，自行删除或者添加，记得从0开始，然后把IBM的url和路都添加进去

~~~
addEventListener(
"fetch",event => {
let url=new URL(event.request.url);
condition = Math.floor(Math.random()*5);
switch(condition)
{
    case 0:
        url.hostname="*********.cf.appdomain.cloud";
        url.pathname="cpPTFwOa6zcqwcXz";
        break;
    case 1:
        url.hostname="******.us-south.cf.appdomain.cloud";
        url.pathname="yMWVYcoi5upYVrfo";
        break;
    case 2:
        url.hostname="******.us-south.cf.appdomain.cloud";
        url.pathname="vVZfr7k1ma5JnwpO";
        break;
    case 3:
        url.hostname="******.us-south.cf.appdomain.cloud";
        url.pathname="oJpq9kXsmy1y081X";
        break;
    case 4:
        url.hostname="*****.us-south.cf.appdomain.cloud";
        url.pathname="CSOpkpjaIDXxEuVU";
        break;
    default:
        url.hostname="www.hostloc.com";
}
let request=new Request(url,event.request);
event. respondWith(
fetch(request)
)
}
)
~~~

**对了，生成的vmess链接里记得把路径去掉，然后把cf works的域名添加上就行**





 
