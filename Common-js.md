常用代码
==

##kkcountdown [JQ倒计时插件]

    <div id="clock" data-time="1420714277"></div>
    
    $("#clock").kkcountdown({
        dayText : '日 ',
        daysText : '日 ',
        hoursText : ':',
        minutesText : ':',
        secondsText : '',
        displayZeroDays : false,
        oneDayClass : false,
        displayDays : false,
        callback : function(){}
    });
 
  http://static.sdg-china.com/avata/js/countdown/kkcountdown.min.js
  
##JQ-Cookie [Jquery Cookie插件]

    var isRead = $.cookie('ffIndexView_web6');
    if(isRead=='1'&&isRead!=null&&isRead!=undefined){
        console.log('');
    }else{
        showTips('popCon3');
        $.cookie('ffIndexView_web6', '1', { expires: 365, path: '/' });
    }
  http://static.sdg-china.com/avata/js/lib/jquery.cookie.js
  
##Tips [Jquery Tips 插件]
    //效果参见 http://award.ff.sdo.com/2014/
    <span class="nam" id="event_6">N卡友情奖</span>
    <span class="nam" id="event_5">N卡显卡专属道具兑换</span>
    
    $('#event_5').add('#event_6').poshytip({
        className: 'tip-darkgray',
        showTimeout: 1,
        alignTo: 'target',
        alignX: 'center',
        offsetY: 5,
        allowTipHover: false,
        fade: false,
        slide: false,
        content: function(updateCallback) {
            return 'TIPS';
        }
    });
    
  http://static.sdg-china.com/avata/js/poshytip/1.2/jquery.poshytip.min.js
  http://static.sdg-china.com/avata/js/poshytip/1.2/tip-darkgray/tip-darkgray.css
  
##Avata ContentShow [弹出层]
    //效果参见 http://award.ff.sdo.com/2014/             
    <a onclick="return showTips('login_div');">登陆</a>
    <div class="popBox" id="login_div">
      <a href="javascript:;" class="btnClose" title="关闭"></a>
      <iframe style="width:440px;height:353px; border:0px;" src="http://login.sdo.com/sdo/Login/LoginFrameFC.php">
      </iframe>
    </div>  
    <div id="mask"></div>
    
    #mask { width: 100%; height: 100%; background: #000; position: absolute; top: 0; left: 0; z-index: 9995; display: none; }
    .popBox { border: 6px solid #e3e3e3; position: absolute; z-index: 9999; display: none; width: 490px; height: 365px; background: #fff; text-align: center; padding-top: 25px }
    .popBox .btnClose { width: 32px; height: 32px; display: block; position: absolute; top: -18px; right: -20px; background: url(//static.sdg-china.com/chd/pic/btnClose.png) no-repeat; }
    
    function showTips(container){
        if(typeof(container) == 'string'){
            container = $("#"+container);
        }
        container.fadeIn(300).css({
            'left':($(window).width()-container.width())/2,
            'top':$(document).scrollTop()+($(window).height()-container.height())/2
        });
        $("#mask").css({
            width:$(window).width(),
            height:$(document).height(),
            opacity:0.5
        }).fadeIn(300);
     
        if(container.height() > $(window).height()) {
            container.css({
                top:$(window).scrollTop()
            });
        }
     
        container.find('.btnClose').click(function(){
            container.fadeOut(300);
            $('#mask').fadeOut(300);
            return false;
        });
    }
