<template>
	<view>
		<view class="main">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
			
				<view class="head">
					<image src="../../static/bookcircle/1.png" mode="widthFix" class="pone" id="p1" @click="tomy">
					</image>
					<view class="name">书 圈</view>
					<image src="../../static/bookcircle/2.png" mode="widthFix" class="pone" id="p2" @click="tocollect">
					</image>
				</view>
			
		</view>

		<view class="overall">
			<view class="main-body" v-for="(item,index) in Backgrounddata" :key="index">
				<view class="maincontent">
					<view class="headone">
						<image :src="item.photo" mode="widthFix" class="avatar"></image>
						<!-- 头像 -->
						<text class="sb">{{item.nameone}}</text> <!-- 名称 -->
					</view>
					<u-read-more class="feeling" :toggle="true" show-height="250">
						<rich-text :nodes="item.content" class="feel"></rich-text>
					</u-read-more>

					<image :src="item.pics" mode="widthFix" class="big"></image> <!-- 照片 -->
					<view class="icon" v-show="isshow" >
						<!-- 小图标 -->
						<image :src="item.address" mode="widthFix" class="sc1" 
							  @click="changeone(item)"></image>
						<image src="../../static/bookcircle/news.png" mode="widthFix" class="sc2"></image>
						<image :src="item.address1"  mode="widthFix" class="sc3" 
							 @click="changetwo(item)"></image>
					</view>

					<view class="comment">
						<text class="txtone">{{item.nametwo}}</text> <!-- 评价 -->
						<text class="txttwo">{{item.comment}}</text>
					</view>
				</view>     
			</view>

		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				Backgrounddata: [{
					address:"../../static/bookcircle/love.png",
					address1:"../../static/bookcircle/start.png",
					photo: require("../../static/bookcircle/people1.png"),
					nameone: "乂氼",
					content: "这本书是我去年买的，书质量没有问题，这本书对于前端开发的性能优化有着很大的帮助，可以提高浏览器的性能，并且简化代码，所以我十分推荐这本书，大家有兴趣的可以去看看",
					pics: require("../../static/bookcircle/book.png"),
					nametwo: "嚩丅",
					comment: ":这个数确实不错，值得一试哈"
				}, {
					address:"../../static/bookcircle/love.png",
					address1:"../../static/bookcircle/start.png",
					photo: require("../../static/bookcircle/people2.png"),
					nameone: "小果子",
					content: "上个月刚刚买的，起初想看的，但是没有时间看，有没有想看的联系我啊，可以低价出售，价格好商量",
					pics: require("../../static/bookcircle/book1.png"),
					nametwo: "小果子",
					comment: ":这个书没有看过，需要的联系我"
				}, {
					address:"../../static/bookcircle/love.png",
					address1:"../../static/bookcircle/start.png",
					photo: require("../../static/bookcircle/people3.png"),
					nameone: "小婷婷啊",
					content: "整本书看完挺有感触的，真的有种说不出的感觉，主人公的一生就是我们很多人需要去经历、去度过的，真的很推荐大家去看看，五星好评",
					pics: require("../../static/bookcircle/book2.png"),
					nametwo: "肖肖",
					comment: ":赞👍👍👍"
				}, {
					address:"../../static/bookcircle/love.png",
					address1:"../../static/bookcircle/start.png",
					photo: require("../../static/bookcircle/people4.png"),
					nameone: "法律人",
					content: "这本书是罗祥老师的经典著作，里面讲了很多人生哲理与法律知识，很有启发意义，内容也易懂,看了这本书之后我才发现我们人真的很渺小，直接冲刷了我的人生观，推荐推荐",
					pics: require("../../static/bookcircle/book3.png"),
					nametwo: "张三",
					comment: ":我得赶紧跑了，溜了溜了小😂"
				}, {
					address:"../../static/bookcircle/love.png",
					address1:"../../static/bookcircle/start.png",
					photo: require("../../static/bookcircle/people5.png"),
					nameone: "冲啊",
					content: "计算机类的同学我强烈建议，看书名就知道重不重要吧😁",
					pics: require("../../static/bookcircle/book4.png"),
					nametwo: "或许有可能吧",
					comment: ":你这网名有点特别哈哈"
				}],

				
				
				iconListtwo:{
					address1:"../../static/bookcircle/clicklove.png",
					address2:"../../static/bookcircle/clickstart.png"
				},
					
				iconListthree:{
					address1:"../../static/bookcircle/love.png",
					address2:"../../static/bookcircle/start.png"
				},
					
				i: "0",
				t: "0",
				decidei: false,
				decidet: false,
				isshow:true,
				updata:true,
				updata2:true

			}
		},
		
		// created:function(){
		// 	this.iconList.map(el => {
		// 		el.isshow = false;
		// 		console.log(create已经执行);
		// 		return el;
		// 	});
		// 	this.iconList2.map(el => {
		// 		el.isshow = false;	
		// 		return el;
		// 	});
		// },
		beforeCreate() {
			
		},
		
		methods: {
			tomy() {
				uni.switchTab({
					url: "../my/my"
				})
			},
			tocollect() {
				uni.navigateTo({
					url: "./sellcet"
				})
			},
			changeone(parameter) {

				// this.iconList.map(el=> {
				// 	el.isshow = false;
				// 	return el;
				// });
				this.decidei = !this.decidei;	
				if (this.decidei) {
					
					parameter.address=this.iconListtwo.address1;
					
				} else {
					
					parameter.address=this.iconListthree.address1;
					
				}
			},
			changetwo(parameter) {
				this.decidet = !this.decidet;
				// this.iconList2.map(el => {
				// 	el.isshow = false;
				// 	return el;
				// });

				if (this.decidet) {
					parameter.address1 = this.iconListtwo.address2;
				
					
				} else {
					parameter.address1 = this.iconListthree.address2;
					
				}
			}
		}
	}
</script>

<style lang="scss">
	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
	}

	.main {
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 100;
		background: rgba(255, 255, 255, 1);
		box-sizing: border-box;
		background-color: #50d8be;
		left: 0;
			.head {
				/* #ifdef MP-WEIXIN */
				//解决微信小程序的胶囊问题
				width: calc(100% - 95px);
				/* #endif */
				/* #ifndef MP-WEIXIN*/
			      width: 100%;
				/* #endif*/
				
				display: flex;
				white-space: nowrap;
				height: 80rpx;
				justify-content: space-between;
				box-sizing: border-box;
				// background-color: yellow;
				align-items: center;
				.name{
					color: white;
				}


				.pone {
					height: 60rpx;
					width: 60rpx;
					margin: 0 15rpx;

				}
			}
		
	}

	.overall {
		.main-body {

			.maincontent {
				margin-top: 150rpx;
				width: 100%;
				min-height: 780rpx;
				margin-bottom: 100rpx;


				// background-color: blue;

				.headone {
					display: flex;
					// background-color: #FEF0F0;
					justify-content: left;
					align-items: center;

					.avatar {
						width: 60rpx;
						height: 60rpx;
						border-radius: 50%;
						margin: 5rpx 15rpx;
					}

					.sb {}
				}

				.feeling {
					width: 98%;
					padding: 0 1%;

					.feel {
						font-size: 35rpx;
					}

				}

				.big {
					width: 98%;
					padding: 0 1%;
					height: 200rpx;
				}

				.icon {
					height: 70rpx;
					width: 98%;
					padding: 0 1%;
					display: flex;
					justify-content: space-between;
					// background-color: red;

					image {
						width: 60rpx;
						height: 60rpx;

					}

					.sc1.active {
						color: red;
					}

				}

				.comment {
					display: flex;
					justify-content: left;
					align-items: center;
					// background-color: gray;
					white-space: wrop;
					width: 98%;
					height-min: 74rpx;
					padding: 0 1%;
					font-size: 35rpx;

					.txtone {
						margin: 0 15rpx;
					}
				}
			}
		}
	}
</style>
