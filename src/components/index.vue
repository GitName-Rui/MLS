<template>
<div id="container">
    <meili-header></meili-header>  
    <router-view></router-view>
    <div id="M-PC-sidebar">
        <div class="options">
            <div class="download-app" @mouseenter="showErweima(true)" @mouseleave="showErweima(false)">
                下载
                <span class="side-vertical">APP</span>
                <div class="erweima">
                    <img src="../assets/img/index/sidebar_erweima_140x140.png"/>
                </div>
            </div>
            <div class="shopping-cart"><router-link to="/cart">购物车</router-link></div>
            <div class="message"><a href="javascript:;">消息</a></div>
            <div class="discount"><a href="javascript:;">优惠券</a></div>
            <div class="collect"><a href="javascript:;">收藏</a></div>
            <div class="footprint"><a href="javascript:;">足迹</a></div>
        </div>
    </div>
    <meili-footer></meili-footer>
</div>
</template>

<script>
import MeiliHeader from './header.vue';
import MeiliFooter from './footer.vue';
export default {
    components:{
        MeiliHeader,
        MeiliFooter
    },
    mounted:function(){       
        //为window绑定scroll事件
        $(window).scroll(()=>{
            //如果滚动距离>=60
            if(document.documentElement.scrollTop>=208)
                //找到id为header-top的div，添加fixed-nav
                $(".nav-title").addClass("fixed-nav");
            else//否则
                //找到id为header-top的div，移除fixed-nav
                $(".nav-title").removeClass("fixed-nav");
        });
    },
    methods:{
        showErweima(bool){
            if(bool){
                $(".options .erweima").css({display:"block"});
            }else{
                $(".options .erweima").css({display:"none"});
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../assets/css/index.css"></style>