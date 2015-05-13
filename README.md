Avata 工作室 WEB 开发规则
==

页面规范
-------------

##公共JS CSS   
使用CDN公网公共JS和CSS库，避免类似JQUERY版本维护问题，常用库提供后发布

##位置和写法
1 文档类型声明及编码
- 统一使用 <!DOCTYPE html> 避免触发quirks模式导致的IE怪异表现
- 编码utf-8 <meta charset="utf-8">

2 资源目录放置及命名   
- css             /project/项目名/css
- js                /project/项目名/js
- widget                /project/项目名/widget               #UI include文件 例如menu.asp nav.asp 
- interface               /project/项目名/interface              #接口文件
- admin      /project/项目名/admin         后台文件  
- 放置
  公共文件可以为 base\.js base\.css config\.inc\.asp   
  指定页面的文件可以为 app.css app.js 也可以和文件名相同 便于查找

      <link href="css/base.css?V1.0" rel="stylesheet" type="text/css">
      <link href="css/index.css?V1.1" rel="stylesheet" type="text/css">
      <script src="js/base.js?v1.0"></script>
      <script src="js/app.js?v1.1"></script>

3 JS 和 CSS 引入文件放在头部标签内，CSS优先   

    <link href="common/style.css?V1.0" rel="stylesheet" type="text/css">
    <script src="js/app.js?v1.3"></script>

4 加载JS 避免使用 window.onload 方式 推荐使用 JQUERY $().ready(function(){ ... }); 避免多个onload导致只加载最后一个   
 
5 外部加载 css js 使用"//cdn.s"而不是"http://cdn.s" 降低下载量 js引入 不写 type="text/javascript"   
 
6 带业务的JS和CSS文件后 加?版本号 如 ?v1.0 避免随即数的缓存失效   
 
7 业务JS 代码放置页面标签内 前 形如   

    <div id='nav'></div>
    ...
    <div>foot</div>
    <script>
      //Js End
      $('#nav').show();
    </script>
    
##低版本IE提示
1 添加在应用和官网的首页，降低用户低版本浏览器使用率   

    <!--[if lte IE 7]> 
    <div style='border: 1px solid #F7941D; background: #FEEFDA; text-align: center; clear: both; height: 75px; position: relative;'>   
        <div style='position: absolute; right: 3px; top: 3px; font-family: courier new; font-weight: bold;'>
            <a href='#' onclick='javascript:this.parentNode.parentNode.style.display="none"; return false;'>
                <img src='//static.sdg-china.com/avata/pic/ie6/ie6nomore-cornerx.jpg' style='border: none;' alt='Close this notice'/>
            </a>
        </div>   
        <div style='width: 640px; margin: 0 auto; text-align: left; padding: 0; overflow: hidden; color: black;'>    
            <div style='width: 75px; float: left;'>
                <img src='//static.sdg-china.com/avata/pic/ie6/ie6nomore-warning.jpg' alt='Warning!'/>
            </div>     
            <div style='width: 275px; float: left; font-family: Arial, sans-serif;'>       
                <div style='font-size: 14px; font-weight: bold; margin-top: 12px;'>
                    您还在使用过时的浏览器
                </div>       
                <div style='font-size: 12px; margin-top: 6px; line-height: 12px;'>
                    为了更好的显示效果和更佳的用户体验，请升级为现代浏览器
                </div>     
            </div>     
            <div style='width: 75px; float: left;'>
                <a href='http://www.firefox.com' target='_blank'>
                    <img src='//static.sdg-china.com/avata/pic/ie6/ie6nomore-firefox.jpg' style='border: none;' alt='Get Firefox 3.5'/>
                </a>
            </div>     
            <div style='width: 75px; float: left;'>
                <a href='http://www.browserforthebetter.com/download.html' target='_blank'>
                    <img src='//static.sdg-china.com/avata/pic/ie6/ie6nomore-ie8.jpg' style='border: none;' alt='Get Internet Explorer 8'/>
                </a>
            </div>     
            <div style='width: 73px; float: left;'>
                <a href='http://www.apple.com/safari/download/' target='_blank'>
                    <img src='//static.sdg-china.com/avata/pic/ie6/ie6nomore-safari.jpg' style='border: none;' alt='Get Safari 4'/>
                </a>
            </div>     
            <div style='float: left;'>
                <a href='http://www.google.cn/intl/zh-CN/chrome/' target='_blank'>
                    <img src='//static.sdg-china.com/avata/pic/ie6/ie6nomore-chrome.jpg' style='border: none;' alt='Get Google Chrome'/>
                </a>
            </div>   
        </div> 
    </div> 
    <![endif]-->
