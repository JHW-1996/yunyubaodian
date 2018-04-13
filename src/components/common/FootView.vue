<template>
  <div>
   <mt-tabbar v-model="selected" fixed>
  <mt-tab-item id="首页">
    <router-link to='/home'>首页<br>home</router-link>
  </mt-tab-item>
  <mt-tab-item id="收藏">
     <router-link to='/fav'>收藏<br>favorite</router-link>
  </mt-tab-item>
  <mt-tab-item id="历史记录">
    <router-link to='/history'>历史记录<br>history</router-link>
  </mt-tab-item>
  <mt-tab-item id="设置">
    <router-link to='/config'>设置<br>config</router-link>
  </mt-tab-item>
</mt-tabbar>
  </div>
</template>

<script>
import { Tabbar, TabItem } from 'mint-ui';
export default {
  data(){
  	return{
  		selected:""
  	}
  }
}
</script>
<style>
  .mint-tabbar{
    width: 100%;
    height: 51px;
    background: #222;
    color: white;
  }
  .mint-tab-item{
    height: 100%;
    padding: 0;
  }
  .mint-tabbar a{
    color: white;
    font-size: 14px;
    display: block;
    width: 100%;
    height: 100%;
    text-decoration: none;
  }
  .mint-tab-item-label{
    height: 100%;
    line-height: 19.5px;
  }
  .mint-tab-item-label a{
    padding-top: 10.5px;
  }
  .mint-tabbar > .mint-tab-item.is-selected{
    background: black;
    box-shadow: 0 2px 8px #fff;
    transition: 0.5s all;
  }
</style>



