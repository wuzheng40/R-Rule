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
- css       -- /project/项目名/css
- js        -- /project/项目名/js
- widget    -- /project/项目名/widget    #UI include文件 例如menu.asp nav.asp 等
- interface -- /project/项目名/interface #接口文件
- admin     -- /project/项目名/admin     #后台文件

  公共文件可以为 base.js base.css config.inc.asp
  指定页面的文件可以为 app.css app.js 也可以和文件名相同 便于查找  形如
  
    <link href="css/base.css?V1.0" rel="stylesheet" type="text/css">
    <link href="css/index.css?V1.1" rel="stylesheet" type="text/css">
    <script src="js/base.js?v1.0"></script>
    <script src="js/app.js?v1.1"></script>
