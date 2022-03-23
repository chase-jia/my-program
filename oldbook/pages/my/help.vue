<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">帮助与反馈</view>
			</view>
		</view>
		<view class="btn"></view>
		<button type="default" class="yj" @click="yjtj()">
			<image src="../../static/shu/xie.png" mode=""></image>
			意见反馈</button>
		<view class="fkk">
			<view class="fk" v-for="(item,index) in liuyanlist" :key="index">
				<text>{{item.content}}</text>
				<input class="inp" type="text" @blur=""  value="" placeholder="请输入" style="border: 2upx #2C405A solid;border-radius: 20upx;padding-left: 20upx;" 
				v-model="item.inputone"/>
				<image :src="item.liuyan" mode="" @click="changecon(item)"></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				syy:{
					url:"../../pages/my/set"
				},
				liuyanlist:[{
					liuyan:"../../static/shu/liuyan.png",
					content:"",
					inputone:""
				}]
			}
		},
		methods: {
			fanhui(e){
				uni.navigateTo({
					url: e.url
				})
			},
			yjtj(){
				var obj = {
					liuyan:"../../static/shu/liuyan.png",
					content:""//用户自己写
				};
				this.liuyanlist.push(obj);
			},
			changecon(parameter){
				parameter.content=parameter.inputone;
				parameter.inputone = "";
			}
			
		}
	}
</script>

<style lang="scss">
	.status_bar {
	  height: var(--status-bar-height);
	  width: 100%;
	  
	 }
	.tou{
		position: fixed;
		height: 100upx;
		width: 100%;
		z-index: 5;
		top: 0;
		left: 0;
		background-color: #50d8be;
		box-sizing: border-box;
		.top{
			width: 100%;
			height: 90upx;
			background-color: #50d8be;
			position: relative;
			display: flex;//弹性布局
			align-items: center;
			justify-content: center;
			.jt{
				position: absolute;
				width: 45upx;
				height: 45upx;
				left: 50upx;
				font-size: 45upx;
				
			}
			.zi{
				position: absolute;
				color: #393939;
				font-size: 45upx;
				border-bottom: 6upx #FFFFFF solid;
				font-weight: bold;
			}
		}
	}
	.btn{
		width: 100%;
		height: 220upx;
	}
	.yj{
			width: 80%;
			margin: 0 auto;//中间
			font-size: 40upx;
			border-radius: 40upx;
			border: 6upx solid #fff890;
			background:linear-gradient(#ffffff,#f7f37d,#FFFFFF);
			image{
				margin-top:20upx;
				width: 50upx;
				height: 50upx;
			}
		
	}
	.fkk{
		position: flex;
		margin: 0 20upx;
		.fk{
			margin-top: 30upx;
			width: 700upx;
			border-radius: 50upx 50upx 0 50upx ;
			height: 300upx;
			padding:20upx;
			position: relative;
			background:linear-gradient(#ffffff,#aaf7ff,#FFFFFF);
			border: 6upx #2B85E4 solid;
			text{
				width: 660upx;
				height: 200upx;
				word-wrap: break-word;
				word-break: keep-all;
				font-size: 25upx;
				font-weight: bold;
			}
			input{
				width:590upx;
				height: 40upx;
				position: absolute;
				bottom: 20upx;
				left: 20upx;
			}
			image{
				width: 40upx;
				height: 40upx;
				position: absolute;
				bottom: 20upx;
				right: 20upx;
			}
		}
	}
</style>
