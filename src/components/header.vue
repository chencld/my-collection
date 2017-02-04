<template>
  <!-- 头部 -->
    <div class="zx_header">
      <div class="header_menu clearfix">
          <a href="javascript:;" @click="toggleFlag" class="zx_menu" v-bind:class="{menu_show:!isShow}" ></a>
          <a href="/" class="logo"></a>
          <a href="/user/message" class="tk_nomsg "></a>
          <a href="/user/info" class="hIcon h_user" title="">
              <img src="http://tva4.sinaimg.cn/crop.0.2.1242.1242.50/9eff8b91jw8fb8qxesx9zj20yi0yndm7.jpg" alt="sakuracld">
          </a>
      </div>
      <div class="leftBox" v-bind:class="{leftHide:isShow}" v-cloak>
          <div class="leftWrap clearfix">
            <a href="/" class="index">首页</a>
            <a href="/activity" class="try">试用</a>
            <a href="/task" class="task">任务</a>
            <a href="/collection" class="collection">原创</a>
          </div>
      </div>
  </div>
</template>

<script>

export default {
  name:"zx_header",
  data() {
      return {
        isShow:true
      }
    },
    methods:{
      toggleFlag: function() {
          this.isShow = !this.isShow;
      }
    }    
};
</script>

<style type="text/css">
  /*头部*/
  .zx_header{width:100%;position: relative;z-index:100;}
  .header_menu{position:relative;width:100%;height: 45px;z-index:2;background:#3d464b;}
  .zx_header .logo{ width:108px; height:45px; background:url(http://zhongce.sina.cn/staticzcwap/images/zc_logo.png) no-repeat left center; background-size:108px 45px; display:block;margin:0 auto;}
  .zx_header .h_user{ top:11px;right:50px; background:url(http://zhongce.sina.cn/staticzcwap/images/person.png?v=1.0) no-repeat 0 0;background-size: 25px auto;width:25px;height:25px;position:absolute;}
  .zx_header .h_user img{border-radius:50%;}
  .h_user img{width:25px;height:25px;}
  .zx_header .tk_nomsg{display: block;position: absolute;width: 23px;height: 45px;right: 12px;top: 0;background: url(http://zhongce.sina.cn/staticzcwap/images/zc_msgs.png) 0 -50px no-repeat;background-size: 23px 200px;}
  .zx_header .tk_msg{width:23px;background-position:0 0;}
  .zx_menu{width:20px;height:45px;display:block;float:left;background-image:url(http://zhongce.sina.cn/staticzcwap/images/zc_menu1.png);background-size:auto 45px;margin-left:13px;}
  .menu_show{background-image:url(http://zhongce.sina.cn/staticzcwap/images/zc_menu2.png);}

  /*左边导航栏*/
  .leftBox{width: 100%;height:60px;position:absolute;top:45px;left: 0;z-index:0;background:#3d464b;overflow:hidden;border-top: 1px solid #575e62;}
  .leftBox{
    -webkit-transform:translate3d(0,0,0);
    transform:translate3d(0,0,0);
    opacity:1;
    -moz-transition:-moz-transform .3s,opacity .3s;
    -o-transition:-o-transform .3s,opacity .3s;
    -webkit-transition:-webkit-transform .3s,opacity .3s;
    transition:opacity .3s,-webkit-transform .3s;
    transition:transform .3s,opacity .3s;
    transition:transform .3s,opacity .3s,-webkit-transform .3s;
  }
  .leftHide{
    -moz-transform:translate3d(0,-100%,0);
    -ms-transform:translate3d(0,-100%,0);
    -webkit-transform:translate3d(0,-100%,0);
    transform:translate3d(0,-100%,0);
    opacity:0;
  }
  .loginBtn{display:block;width: 80px;line-height: 25px;text-align: center;font-size: 12px;color: #fff;margin:20px auto;background: #4d97c5;border-radius: 3px;}
  .leftInfo{overflow:hidden;}
  .leftWrap{width:312px;position: relative;text-align: center;margin:0 auto;}
  .leftWrap a{font-size:13px;color:#fff;background: url('http://zhongce.sina.cn/staticzcwap/images/zc_tags.png?v=2.0') 0 -322px no-repeat;background-size: 250px auto;display:block;width:78px;float:left;overflow:hidden;line-height:88px;}
  .leftWrap a.index{background-position:-200px -388px;}
  .leftWrap a.try{background-position:28px -323px;}
  .leftWrap a.task{background-position:-202px -322px;}
  .leftWrap a.collection{background-position:26px -388px;}

</style>






