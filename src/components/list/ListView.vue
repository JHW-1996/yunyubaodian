<template>
	<div class="box">
	<mt-header :title="title"  class='header-color'>
	  <router-link to="/" slot="left">
	    <mt-button icon="back">返回</mt-button>
	  </router-link>
	  <mt-button icon="收藏" slot="right"></mt-button>
	</mt-header>
		<ul>
		
			<li v-for='(item,index) in arr'>
				<router-link :to="{
					path:'/article',
					params:{userId:123},
					query:{
					names:str,
					idx:index
					
					}
				}">
				<img :src="require('../../assets/img/tu/'+item.img)
				">
					<p>{{item.title}}</p>
				</router-link>
				
			</li>
		</ul>
	</div>
</template>
<script>
import '../../mock/mock'
 export default{
 	data(){
 		return {
 			arr:[],
 			str:"",
 			title:""
 		}
 	},
 	mounted(){
 		let id=this.$route.params.id;
 		this.str=id;
 		this.$http({
 			method:'get',
 			url:'/arList'
 		})
 		.then(res=>{
 			this.title=res.data[id]['home_title']
 			this.arr=res.data[id]['fenlei'];
 		})
 	}
 }

</script>
<style scoped>
ul li{
	width: 100%;
	padding: 15px 0 15px 40px;
	border-bottom: dashed 1px #000; 
	font-size: 16px;
	list-style:none;
}
ul li a{
	text-decoration:none;
	color:#000;
	display: flex;
}
ul li img{
	width: 70px;
	height: 70px;
	border-radius: 50%;
}
.header-color{
	background: #990000;
}
p{
	line-height:70px;
	margin-left: 60px;
}
</style>