<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
			  <!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<text class="head_txt">商品详情</text>
			</view>
		</view>
		v<view class="top">
			<image src="../../static/shudan/4.jpg" mode="" @click="toGeren"></image>
			<view class="top1">
				<text class="top11">老笔斋的老猫</text>
				<text class="top12">刚刚来过</text>
			</view>
		</view>
		<view class="jiage">
			<text class="jiage1">￥16</text>
			<text class="jiage2">原价￥22.6</text>
			<text class="jiage3">支持自提</text>
		</view>
		 <view class="tupian">
		    <scroll-view  scroll-x="true" @scroll="scroll" scroll-left="120">
		        <image class="tp1" src="../../static/shudan/4.jpg" mode=""></image>
				<image class="tp2" src="../../static/shudan/5.jpg" mode=""></image>
				<image class="tp3" src="../../static/shudan/6.jpg" mode=""></image>
		    </scroll-view>
		</view>
		<view class="xinxi">
			<view class="xinxil">
				<text>作者</text>
				<text>出版社</text>
				<text>ISBN</text>
				<text>品相</text>
			</view>
			<view class="xinxir">
				<text>王小波</text>
				<text>北京出版社</text>
				<text>9787530216590</text>
				<text>九成新</text>
			</view>
		</view>
		<view class="spxq">
			<text>商品详情</text>
		</view>
		<view class="xq">
			<text>你房产税的年龄段奴隶少女冻市场立法什么看没看拜拜四百次说可能措施摆死了女</text></br>
			<text>视频模命中率冒泡老师们盘的攀本次不死你是啊你为弄清偶问你地为你你哦玩得起爬阿莫安慰</text>
		</view>
		<view class="hd">
			<text>互动</text>
		</view>
		<view class="ly">
			<image src="../../static/shudan/6.jpg" mode=""></image>
			<view class="input">
				<input type="text" value="" placeholder="问问更多细节吧~"/>
				<view class="ly1">
					<text>留言</text>
				</view>
			</view>
		</view>
		<view class="gm">
			<view class="gm1">
				<image :src="src" mode="" @click="changeColor"></image>
				<text>喜欢</text>
			</view>
			<view class="gm2">
				<image src="../../static/xiangqing/3.png" mode=""></image>
				<text>待会聊</text>
			</view>
			<view class="gm3" @click="toLiaotian">
				<text>聊一聊</text>
			</view>
			<view class="gm4">
				<text>马上买</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false,
				src:"../../static/xiangqing/1.png",
				scrollLeft: 0,
				old: {
				    scrollLeft: 0
				}
			}
		},
		methods: {
			toBack(){
				uni.navigateTo({
					url:"./resou"
				});
			},
				changeColor(){
					this.show=!this.show,
					this.show?this.src="../../static/xiangqing/2.png":this.src="../../static/xiangqing/1.png"
				},
				 scroll: function(e) {
				        console.log(e)
				        this.old.scrollLeft = e.detail.scrollLeft
				        },
				toGeren(){
					uni.navigateTo({
						url:"./genren"
					})
				},
				toLiaotian(){
					uni.navigateTo({
						url:"./liaotian"
					})
				}
		}
	}
</script>

<style lang="scss">
.status_bar {
		height: var(--status-bar-height);
		width: 100%;
}
.head_bg{
	z-index: 100;
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	background-color: #50d8be;
	border-radius: 0 0 100rpx 100rpx;
	.head{
		height: 100rpx;
		/* #ifdef MP-WEIXIN */
		width: calc(100% - 95px);
		/* #endif */
		/* #ifndef MP-WEIXIN */
		width: 100%;
		/* #endif */
		image{
			height: 38rpx;
			width: 38rpx;
			margin-left: 50rpx;
			margin-top: 31rpx;
		}
		.head_txt{
			font-size: 45rpx;
			font-weight: bold;
			color: white;
			margin-left: 215rpx;
		}
	}
}
.top{
	width: 700rpx;
	height: 100rpx;
	background-color: #ffffff;
	margin:150rpx 25rpx 0 25rpx;
	border-radius: 30rpx;
	display: flex;
	box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
	image{
		width: 80rpx;
		height: 80rpx;
		border-radius: 40rpx;
		margin-left: 35rpx;
		margin-top: 10rpx;
	}
	.top1{
		width: 180rpx;
		height: 100rpx;
		margin-left: 30rpx;
		padding-top: 20rpx;
		.top11{
			// width: 170rpx;
			height: 30rpx;
			font-size: 30rpx;
			margin-top: 20rpx;
		}
		.top12{
			font-size: 25rpx;
			color: #808080;
		}
	}
}
.jiage{
	width: 100%;
	height: 90rpx;
	margin-top: 20rpx;
	.jiage1{
		font-size: 50rpx;
		font-weight: bold;
		color: #50d8be;
		margin-left: 30rpx;
		line-height: 90rpx;
	}
	.jiage2{
		font-size: 30rpx;
		color: #808080;
		margin-left: 35rpx;
		line-height: 90rpx;
		text-decoration: line-through;
	}
	.jiage3{
		font-size: 30rpx;
		font-weight: bold;
		color: #50d8be;
		margin-left: 255rpx;
		line-height: 90rpx;
	}
}
.tupian{
	height: 400rpx;
	background-color: #ffffff;
	margin-top: 80rpx;
	display: flex;
	position: relative;
	overflow: hidden;
	.tp1{
		width: 400rpx;
		height: 400rpx;
		position: absolute;
		left: 0;
		top: 0;
	}
	.tp2{
		width: 400rpx;
		height: 400rpx;
		position: absolute;
		left: 410rpx;
		top: 0;
	}
	.tp3{
		width: 400rpx;
		height: 400rpx;
		position: absolute;
		left: 820rpx;
		top: 0;
	}
}
.xinxi{
	width: 700rpx;
	height: 245rpx;
	background-color: #ffffff;
	margin: 35rpx 25rpx 0 25rpx;
	border-radius: 25rpx;
	padding-left: 50rpx;
	display: flex;
	box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
	.xinxil,.xinxir{
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
		font-size: 30rpx;
		color: #808080;
	}
	.xinxir{
		margin-left: 90rpx;
	}
}
.spxq{
	height: 70rpx;
	line-height: 70rpx;
	margin-left: 25rpx;
	font-size: 30rpx;
	font-weight: bold;
	color: #50d8be;
}
.xq{
	width: 700rpx;
	height: 235rpx;
	background-color: #ffffff;
	margin: 0 auto;
	padding: 25rpx 40rpx 0 50rpx;
	font-size: 30rpx;
}
.hd{
	height: 60rpx;
	line-height: 60rpx;
	margin-left: 25rpx;
	font-size: 30rpx;
	font-weight: bold;
	color: #50d8be;
}
.ly{
	height: 140rpx;
	width: 100%;
	display: flex;
	image{
		width: 84rpx;
		height: 84rpx;
		border-radius: 42rpx;
		margin-left: 55rpx;
		margin-top: 30rpx;
	}
	.input{
		width: 530rpx;
		height: 80rpx;
		background-color: #ffffff;
		margin-left: 30rpx;
		margin-top: 30rpx;
		border-radius: 0 20rpx 20rpx 0;
		padding-top: 15rpx;
		padding-left:10rpx;
		position: relative;
		.ly1{
			width: 130rpx;
			height: 80rpx;
			background-color: #50d8be;
			text-align: center;
			line-height: 80rpx;
			font-size: 35rpx;
			font-weight: bold;
			color: white;
			border-radius: 0 20rpx 20rpx 0;
			position: absolute;
			top: 0;
			right: 0;
		}
	}
}
.gm{
	height: 140rpx;	
	width: 100%;
	background-color: #ffffff;
	display: flex;
	.gm1{
		width: 60rpx;
		height: 100rpx;
		margin-left: 55rpx;
		margin-top: 25rpx;
		display: flex;
		flex-direction: column;
		font-size: 30rpx;
		color: #808080;
		image{
			width: 50rpx;
			height: 50rpx;
		}
	}
	.gm2{
		width: 90rpx;
		height: 100rpx;
		margin-left: 55rpx;
		margin-top: 25rpx;
		display: flex;
		flex-direction: column;
		font-size: 30rpx;
		color: #808080;
		image{
			width: 50rpx;
			height: 50rpx;
			margin-left: 15rpx;
		}
	}
	.gm3{
		width: 200rpx;
		height: 95rpx;
		background-color: #83af2c;
		margin-left: 45rpx;
		margin-top: 20rpx;
		border-radius: 20rpx;
		font-size: 45rpx;
		color: white;
		text-align: center;
		line-height: 95rpx;
		box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
	}
	.gm4{
		width: 200rpx;
		height: 95rpx;
		background-color: #50d8be;
		margin-left: 30rpx;
		margin-top: 20rpx;
		border-radius: 20rpx;
		font-size: 45rpx;
		color: white;
		text-align: center;
		line-height: 95rpx;
		box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
	}
}
</style>

