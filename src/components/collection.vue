<style type="text/css">
    /*list*/
    .allList{width: 100%;position: relative;margin-top: 10px;background: #fff;}
    .listTab{width: 100%;height: 40px;overflow: hidden;background: #fff;z-index: 10;border-bottom: 1px solid #e1e1e1;margin-bottom:10px;}
    .list_fix{position: fixed;top: 0;}
    .listTab a{display: block;line-height: 38px;width: 25%;float: left;font-size: 15px;text-align: center;}
    .listTab a.selected{border-bottom: 2px solid #4b5c66;}
    .listTab a.all{font-size: 17px;color: #fff;background: #4b5c66;border-bottom: 2px solid #4b5c66;}
    .listTab2{padding:16px 0;height: 24px;}
    .listTab2 a{display: block;float:left;width: 42px;line-height: 24px;text-align: center;font-size: 12px;color: #acacac;background: #f1f1f1;margin-left: 13px;border-radius: 3px;}
    .listTab2 a.selected{background: #5098c3;color:#fff;}
    #listCon{min-height:680px;}
    .listCon{position: relative;display: none;}
    .listShow{display: block;}
    .listCon li{height:100px;margin-bottom:18px;}
    .listCon li .items{display: block;height: 100px;position: relative;margin:0 13px;}
    .listCon li .pic{width: 150px;height: 100px;display: block;float: left;margin-right: 12px;}
    .listCon li .kind{position: absolute;left:0;top: 0;display: block;width: 37px;line-height: 17px;text-align: center;font-size: 11px;color: #fff;}
    .listCon li .kind1{background: #fd5c5f;}
    .listCon li .kind2{background: #68c88a;}
    .listCon li .kind3{background: #4d97c5;}
    .listCon li .essence{font-size: 14px;height:46px;line-height: 23px;overflow: hidden;text-indent:50px;}
    .listCon li .noessence{background:none;text-indent:0px;}
    .listCon li .essence1{background-position:0 -77px;}
    .listCon li .essence2{background-position:0 -127px;}
    .listCon li .author{display: block;height: 23px;line-height: 23px;margin-top: 20px;color: #acacac;font-size: 12px;padding-bottom:8px;border-bottom: 1px solid #e1e1e1;margin-left:162px;}
    .listCon li .author .t{float: right;}
    .listCon li .author a{color: #acacac;display:block;width: 76%;overflow: hidden;height: 23px;white-space:nowrap; text-overflow:ellipsis;line-height:23px;}
    .listCon li .author .headp{display:block;width: 23px;height: 23px;border-radius: 50%;margin-right: 6px;float:left;}
    .listCon li .author a span{float:left;max-width:50%;overflow: hidden;white-space:nowrap; text-overflow:ellipsis;}
    .listCon li .author em{float:left;width:16px;height:22px;background:url(http://zhongce.sina.cn/staticzcwap/images/zc_w_verify2.png) 4px center no-repeat;display:block;background-size:12px 12px;}
    /*加载更多*/
    .zx_loading{ height:20px; line-height: 20px; text-align: center; padding-bottom: 10px;}
    .zx_loading .load_btn{ font-size:14px; color:#616161; display: inline-block;padding-left:30px;position: relative;}
    .zx_loading .load_btn:before{content:''; width:18px; height:18px; position:absolute; left: 0; top:2px; -webkit-animation: loading 1.1s linear infinite; -moz-animation: loading 1.1s linear infinite;  animation: loading 1.1s linear infinite;background: url(http://zhongce.sina.cn/staticzcwap/images/zc_loading_icon.png) no-repeat left center; background-size:18px auto;}
    /*固定浮层*/
    .fiex_btn{ position:fixed;width:44px; right:7px; bottom:50px;}
    .fiex_btn .up_btn{ width:44px; height:44px; background:rgba(0,0,0,.5); border-radius:50%; display: inline-block; position:relative;}
    .fiex_btn a.up_btn:active,.fiex_btn a.up_btn:hover{background:rgba(0,0,0,.8);}
    .fiex_btn .up_btn:before{ content:''; position:absolute; top:17px; left:12px;  border-style: solid; border-width: 1px 1px 0 0; border-color: #fff; display: inline-block; height: 20px; width: 20px; transform: rotate(-45deg); -webkit-transform: rotate(-45deg);}

    @keyframes loading {
        from {
            -webkit-transform: rotate(0deg) translateZ(0)
        }

        to {
            -webkit-transform: rotate(360deg) translateZ(0)
        }
    }

    @-moz-keyframes loading {
        from {
            -webkit-transform: rotate(0deg) translateZ(0)
        }

        to {
            -webkit-transform: rotate(360deg) translateZ(0)
        }
    }

    @-webkit-keyframes loading {
        from {
            -webkit-transform: rotate(0deg) translateZ(0)
        }

        to {
            -webkit-transform: rotate(360deg) translateZ(0)
        }
    }

</style>
<template>
    <div class="lists">
        <!-- 报告列表 -->
        <div class="allList" id="allList">
            <div class="listTab clearfix" id="listTab1" v-on:click="_tabChange1">
                <a href="javascript:;" v-bind:class="tabClass[0]" data-type="0">全部原创</a>
                <a href="javascript:;" v-bind:class="tabClass[1]" data-type="1">报告</a>
                <a href="javascript:;" v-bind:class="tabClass[2]" data-type="2">作业</a>
                <a href="javascript:;" v-bind:class="tabClass[3]" data-type="3">投稿</a>
            </div>
            <div id="listCon" class="clearfix">
                <ul class="listCon listShow">
                    <li v-for="articles in artDatas" v-on:click="_location" v-bind:url="articles.url">
                        <div class="items">
                            <img :src="articles.cover" class="pic">
                            <template v-if="articles.type==1">
                                <span class="kind kind1">报告</span>
                                <template v-if="articles.essence==1">
                                    <p class="essence essence1">{{articles.title}}</p>
                                </template>
                                <template v-else>
                                    <p class="essence noessence">{{articles.title}}</p>
                                </template>
                            </template>
                            <template v-else-if="articles.type==6">
                                <span class="kind kind2">作业</span>
                                <template v-if="articles.essence==1">
                                    <p class="essence essence2">{{articles.title}}</p>
                                </template>
                                <template v-else>
                                    <p class="essence noessence">{{articles.title}}</p>
                                </template>
                            </template>
                            <template v-else-if="articles.type==2">
                                <span class="kind kind3">投稿</span>
                                <template v-if="articles.essence==1">
                                    <p class="essence essence1">{{articles.title}}</p>
                                </template>
                                <template v-else>
                                    <p class="essence noessence">{{articles.title}}</p>
                                </template>
                            </template>
                            <p class="author">
                                <span>{{articles.arttime}}</span>
                                <a v-bind:href="'http://zhongce.sina.cn/space/index?uid='+articles.weibo.uid">
                                <img :src="articles.weibo.avatar_large" class="headp">{{articles.weibo.screen_name}}</a>
                            </p>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
        <div class="zx_loading" v-if="!loadTag">
            <a href="javascript:;" class="load_btn">加载中</a>
        </div>
        <!-- 滚动到顶部 -->
        <div class="fiex_btn" v-if="fixTag" v-on:click="_top">
            <a href="javascript:;" class="up_btn"></a>
        </div>
    </div>
</template>
    <script type="text/javascript">
        var doc = document;
        // body...
        var _scriptOnload = doc.createElement('script').readyState ?
            function(node, callback) {
                var oldCallback = node.onreadystatechange;
                node.onreadystatechange = function() {
                    var rs = node.readyState;
                    if (rs === 'loaded' || rs === 'complete') {
                        node.onreadystatechange = null;
                        oldCallback && oldCallback();
                        callback.call(this);
                    }
                };
            } : function(node, callback) {
                node.addEventListener('load', callback, false);
            };
        var _getScript = function(url, fn) {
            var node = doc.createElement('script'),
                heads = doc.getElementsByTagName('head')[0] || doc.documentElement;
            node.src = url;
            node.async = true;
            _scriptOnload(node, function() {
                fn && fn.call(node, '');
                if (heads && node.parentNode) {
                    heads.removeChild(node);
                }
            });
            heads.insertBefore(node, heads.firstChild);
            return node;
        }
        
        export default {
            name:"lists",
            data: function() {
                return {
                    type:0,
                    essence:0,
                    pageIndex:1,
                    artDatas:[],
                    loadTag:true,
                    fixTag:false,
                    tabClass:["all selected","","",""]
                }
            },
            created: function(){
                this.loadDatas();
            },
            mounted:function(){
                var that = this;
                window.onscroll = function(){
                    //that.loadDatas();
                    var top1 = document.body.scrollTop || document.documentElement.scrollTop,
                        top2 = window.screen.height,
                        top3 = document.body.scrollHeight || document.documentElement.scrollHeight;
                    if(top1>top3-top2-50) that.handleScroll();
                    if(top1>top2) that.fixTag=true;
                    else that.fixTag=false;
                }
            },
            methods:{
                _top:function(){
                    document.body.scrollTop = 0;
                },
                _location:function(event){
                    console.log(event);
                    var url = event.currentTarget.getAttribute("url");
                    location.href=url;
                },
                handleScroll:function(){
                    var that = this,
                        loadTag = that.loadTag;
                    if(loadTag){
                        that.pageIndex+=1;
                        that.loadTag=false;
                        that.loadDatas();
                    }
                },
                loadDatas:function(){
                    var that = this,
                        pageIndex = that.pageIndex,
                        type=that.type,
                        essence=that.essence;
                    window.myCollection = function(d){
                        //var d=JSON.parse(d);
                        if(d.result.status.code==0){
                            if(d.result.data.list&&d.result.data.list.length>0){
                                that.artDatas=that.artDatas.concat(d.result.data.list);
                                that.loadTag=true;
                            }
                        }
                        else alert(d.result.status.msg);
                    }
                    var tempUrl="http://zhongce.sina.com.cn/collection/lists/?format=json&pageSize=10&type="+type+"&essence="+essence+"&page="+pageIndex+"&callback=myCollection";
                    
                    _getScript(tempUrl);
                },
                _tabChange1:function(ev){
                    var ev = ev || event,
                        tar = ev.target || ev.srcElement,
                        par = tar.parentNode,
                        type = tar.getAttribute("data-type");
                    var tempArr=["all","","",""];
                        tempArr[type]+=" selected";
                        this.pageIndex=1;
                        this.type=type;
                        this.loadTag=false;
                        this.artDatas=[];
                        this.tabClass=tempArr;
                        this.loadDatas();
                },
            }
        }
    </script>
</body>
</html>















