<template>
    <div class="sliderwrap" id="sliderwrap">
        <swiper :options="swiperOption" v-cloak>
            <swiper-slide class="slider_item">
                <a href="http://zhongce.sina.com.cn/article/view/1884/">
                    <img src="http://s.img.mix.sina.com.cn/auto/resize?size=560_0&amp;img=http%3A%2F%2Fsinastorage.com%2Fstorage.miaosha.sina.com.cn%2Fproducts%2F201701%2F7dab46b03fdcf300f12418fead46357b.jpg">
                    <span class="kind kind3">投稿</span>
                    <span class="mask"></span>
                    <span class="essence essence1">新浪众测达人孵化计划启动：千万资源免费给你</span>
                </a>
            </swiper-slide>
            <swiper-slide class="slider_item">
                <a href="http://zhongce.sina.com.cn/article/view/1972/">
                    <img src="http://s.img.mix.sina.com.cn/auto/resize?size=560_0&amp;img=http%3A%2F%2Fsinastorage.com%2Fstorage.miaosha.sina.com.cn%2Fproducts%2F201701%2Fba7420ef9e44176e081e4079a77b3329.jpg">
                      <span class="kind kind3">投稿</span>
                      <span class="mask"></span>
                      <span class="essence noessence">新浪众测大数据，拼命想送礼，你还不知道吗？</span>
                </a>
            </swiper-slide>
            <swiper-slide class="slider_item">
                <a href="http://zhongce.sina.com.cn/article/view/1990/">
                    <img src="http://s.img.mix.sina.com.cn/auto/resize?size=560_0&amp;img=http%3A%2F%2Fsinastorage.com%2Fstorage.miaosha.sina.com.cn%2Fproducts%2F201701%2F947835a436667695d3771f9fb079873c.jpg">
                      <span class="kind kind3">投稿</span>
                      <span class="mask"></span>
                      <span class="essence essence1">理科男翻包包，晒晒我的日常数码出行装备</span>
                </a>
            </swiper-slide>
                
            <swiper-slide class="slider_item">
                <a href="http://zhongce.sina.com.cn/report/view/1773/">
                  <img src="http://sinastorage.com/storage.miaosha.sina.com.cn/products/201701/7a4fb6bc6ff1b926ba15563943662652.jpg">
                      <span class="kind kind1">报告</span>
                      <span class="mask"></span>
                      <span class="essence essence1">回到小城使用畅享6S，售楼小妹觉得还不错</span>
                </a>
            </swiper-slide>
            <swiper-slide class="slider_item">
                <a href="http://zhongce.sina.com.cn/article/view/2000/">
                    <img src="http://sinastorage.com/storage.miaosha.sina.com.cn/products/201701/f31c8fb2348cbbbfa8a341c9e6971632.jpg">
                        <span class="kind kind3">投稿</span>
                        <span class="mask"></span>
                        <span class="essence noessence">从触控走向交谈，没准是人工智能的下一个风口</span>
                </a>
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import '../../static/css/swiper.css'

export default {
  name:"sliderwrap",
  components: {
      swiper,
      swiperSlide
  },
  data() {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          paginationClickable: true,
          speed: 1000,
          loop: true,
          autoplay: 0,
          autoplayDisableOnInteraction: false
        }
      }
    }    
};
</script>








