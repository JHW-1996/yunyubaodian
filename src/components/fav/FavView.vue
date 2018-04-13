<template>
	<div class="fav">
		<mt-header fixed title="收藏" class='header-color'></mt-header>

		<div class="fav-main">
			<ul>
      		<li v-for="item in arr">
      			{{item}}
      		</li>
      	</ul>

		</div>
	</div>
</template>
<script>
export default{
		data(){
			return{
				val:'',
				arr:[]
			}
		},
		mounted(){
			
			var ls=localStorage;
			var str=''
			var val=ls.getItem("f")
			var arr=JSON.parse(val)
			arr.forEach(item =>{
				str+='a'+item
			});
			var brr=str.split('a')
			this.arr=brr
		}
	}

</script>	
<style scoped>
*{
	margin: 0;
	padding: 0;
}
.fav{
	width: 100%;
	height: 100%;
	position: absolute;
	left: 0px;
	top: 0px;
}
.fav-main{
	margin-top: 40px;
}
.header-color{
	background: #990000;
}
</style>
