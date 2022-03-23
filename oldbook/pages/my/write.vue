<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">编辑</view>
			</view>
		</view>
		<view class="emp">	
		</view>
		<view class="txiang">
			<view class="tx">头像</view>
			<image src="../../static/shu/touxiang.jpg" mode=""></image>
		</view>
		<view class="xiugai" v-for="(item,index) in xiugai" :key="index">
			<text class="tx">{{item.name}}</text>
			<input type="" value="" placeholder="请输入" placeholder-style="color: #5bf9da;font-size: 30upx;direction:rtl" style="text-align: right;cursor:100upx"/>
		</view>
		<button type="default" class="accomplish">
			<text>完成</text>
		</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				syy:{
					url:"../../pages/my/my"
				},
				xiugai:[{
					name:"昵称",
					value:"可爱的巴扎黑"
				},{
					name:"性别",
					value:"女"
				},{
					name:"生日",
					value:"2020-07-27"
				},{
					name:"个性签名",
					value:"真的不写点什么吗~"
				}]
			}
		},
		methods: {
			fanhui(e){
				uni.switchTab({
					url: e.url
				})
			},
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
	.emp{
		width: 100%;
		height: 200upx;
	}
	.txiang{
		width: 100%;
		height: 200upx;
		box-sizing: border-box;
		display: flex;//弹性盒子
		align-items: center;
		justify-content: space-between;
		margin-top: 20upx;
		border-top: 6upx #c7c7c7 dashed;
		border-bottom: 6upx #c7c7c7 dashed;
			image{
			margin-right: 50upx;
			width: 130upx;
			height: 130upx;
			border-radius: 50%;
			}
	}
	.xiugai{
		width: 100%;
		height: 150upx;
		box-sizing: border-box;
		display: flex;//弹性盒子
		align-items: center;
		justify-content: space-between;
		margin-top:10upx;
		border-top: 6upx #c7c7c7 dashed;
		border-bottom: 6upx #c7c7c7 dashed;
		input{
			margin-right: 50upx;
			color: #50d8be;
			font-size: 30upx;
		}
	}
	.accomplish{
		margin-top: 70upx;
		background-color: #8de7e8;
		width: 250upx;
		height: 100upx;
		display: flex;
		line-height: 100upx;
		border-radius: 50upx;
		text{
			padding-left: 30%;
		}
	}
</style>