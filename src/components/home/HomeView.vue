<template>
	<div class="home">
		<mt-header fixed title="孕育宝典" class='header-color'></mt-header>
		<div class="container">
				<ul>
					<router-link tag='li' to='/list/yunqian'>
						<img src="../../assets/img/pic1.png" alt="">
					</router-link>

					<router-link tag='li' to='/list/yunzhong'>
						<img src="../../assets/img/pic2.png" alt="">
					</router-link>

					<router-link tag='li' to='/list/chanqian'>
						<img src="../../assets/img/pic3.png" alt="">
					</router-link>

					<router-link tag='li' to='/list/chanhou'>
						<img src="../../assets/img/pic4.png" alt="">
					</router-link>

					<router-link tag='li' to='/list/chengzhang'>
						<img src="../../assets/img/pic5.png" alt="">
					</router-link>

					<router-link tag='li' to='/list/fangzhi'>
						<img src="../../assets/img/pic6.png" alt="">
					</router-link>
				</ul>
		</div>
	</div>

</template>
<script>
import { Header } from 'mint-ui';
export default{

}
</script>
<style scoped>
*{
	margin: 0;
	padding:0;
}
.home{
	width: 100%;
	height: 100%;
	position: absolute;
	left: 0px;
	top: 0px;
}
.container{
	margin-top: 40px;
}
.container ul li{
	list-style: none;
	padding:10px 0 10px 0;
}
.container ul img{
	width: 80%;
	height: 90%;
	display: block;
	margin-left:auto;
	margin-right: auto;
	text-align: center;
}
.header-color{
	background: #990000;
}
</style>