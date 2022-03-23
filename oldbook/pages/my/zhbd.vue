<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">账户绑定</view>
			</view>
			<view class="xz">
				<view class="bd" v-for="(item,index) in bdlist" :key="index">
					<u-popup class="tanchu" v-model="item.show" mode="bottom" border-radius="20" width="100%" height="50%">
						<view class="name">已绑定{{item.name}}</view>
						<button type="default">一键解绑</button>
					</u-popup>
					<u-button class="btn" @click="tellme(item)">绑定{{item.name}}
					<image src="../../static/shu/jtx.png" mode=""></image></u-button>
				</view>
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
				bdlist:[{
					show:false,
					name:"手机号",
					haoma:"13564738",
				},{
					show:false,
					name:"微信号",
					haoma:"13564738",
				},{
					show:false,
					name:"QQ号",
					haoma:"13564738",
				}]
			}
		},
		methods: {
			fanhui(e){
				uni.navigateTo({
					url: e.url
				})
			},
			tellme(ww){
				ww.show=true;
				
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
	.xz{
		margin-top: 40upx;
		.btn{
			margin-top: 50upx;
			color: #50d8be;
			height: 100upx;
			font-size: 40upx;
			font-weight: bold;
			image{
				width: 30upx;
				height: 30upx;
			}
		}
		.tanchu{//弹出样式
			.name{
				margin: 50upx 0;
				width: 100%;
				text-align: center;
				color: #50d8be;
				font-size: 40upx;
				font-weight: bold;
			}
			button{
				width: 80%;
				margin: 0 auto;//中间
				font-size: 40upx;
				border-radius: 40upx;
				border: 6upx solid #fff890;
				background:linear-gradient(#65b7ff,#c1c324);
			}
		}
	}
</style>
