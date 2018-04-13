<template>
	<div class="ddd">
		<mt-header title="文章内容"  class='header-color'>
	    <mt-button icon="back" slot="left" @click="returns">返回</mt-button>
	  <mt-button icon="收藏" slot="right" @click='f1'>收藏</mt-button>
	</mt-header>
		<p>{{content}}</p>
	</div>
</template>
<script>
export default{
	data(){
		return{
			content:"",
			title:""

		}
	},
	methods:{
		returns(){
			this.$router.history.go(-1)
		},
		f1(){
			var ls = localStorage;
			var num=''
			if(!ls.getItem("f")){
				var arr =ls.setItem('f',"[]")
			}
			var brr=JSON.parse(ls.getItem('f'))
			if (brr.includes(this.title)) {
				alert('已收藏')
			}else{
				brr.push(this.title)
				alert('收藏成功')
			}
			brr.forEach(item => {
				num += item
			});
			var jsondata=JSON.stringify(brr)
			ls.setItem('f',jsondata)
		}

	},
	mounted(){
		let names = this.$route.query.names;
		let idx = this.$route.query.idx;
		this.$http({
 			method:'get',
 			url:'/arList'
 		})
 		.then(res=>{
 			this.content=res.data[names]['fenlei'][idx].content;
 			this.title=res.data[names]['fenlei'][idx].title;
 			
 		})
	}
}
</script>
<style scoped>
.ddd{
	width: 100%;
	height: 100%;
	position: absolute;
	top: 0px;
	left: 0px;

}
.header-color{
	background: #990000;
}
p{
	font-size: 16px;
	padding: 20px;
	line-height: 35px;
	color: #063889;
}
</style>
