<template>
	<view>

		<view class="login">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/bookcircle/remove.png" mode="widthFix" @click="remove"></image>
				<text>注册</text>
			</view>
		</view>

		<view class="logo">
			<image src="../../static/otherphoto/logo.png" mode="widthFix"></image>
		</view>
		<view class="famousremarks">
			<text>人生在勤-不索何获</text>
		</view>

		<view class="inputsr">
			<view class="inputone" :style="{'border-Color':bbb}">
				<input type="text" value="" placeholder="账号/手机号码" v-model="accounts" @focus="judge" @blur="lose" />
			</view>
			<view class="inputtwo" :style="{'border-Color':ccc}">
				<input type="password" value="" placeholder="请输入密码" v-model="accountsone" @focus="showToast"
					@blur="loseone" />
			</view>
			<view class="inputthree">
				<input type="text" value="" placeholder="绑定电话号码" v-model="accountsthree" />
			</view>
		</view>

		<!-- <u-toast ref="uToast" :duration='200' />-->
		<!-- 判断组件 -->

		<view class="consult">
			<view class="checkbox" @click="clicked" :style="{'backgroundColor':sss}"></view>
			<text>已阅读且同意老书循环用户协议和隐私政策</text>
		</view>

		<view class="protocol">
			<u-button :custom-style="customStyle" type="primary" shape="circle" :disabled="islog" @click="tosubmit">注册
			</u-button>
		</view>
		<u-modal v-model="show" width="70%" :title="title1"></u-modal>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				exist: false,
				accounts: "",
				accountsone: "",
				accountsthree: "",
				bbb: "#50d8be",
				ccc: "#50d8be",
				sss: "#f0f0f0",
				isclick: false,
				val1: false,
				val2: false,
				title1: "",
				// show: true,
				show: false,
				title: "",
				customStyle: {
					height: "95rpx"
				}
			}
		},
		computed: {
			islog() {
				if (this.accounts.trim() && this.accountsone.trim() && this.isclick) {
					return false;
				} else {
					return true;
				}
			}
		},
		methods: {
			remove() {
				uni.navigateBack({
					url: "./login"
				})
			},
			showToast() {
				if (!this.accounts.trim()) {
					// this.$refs.uToast.show({
					// 	title: '请输入用户名',
					// 	type: 'error'
					// });
					this.ccc = "#50d8be";

				}
			},
			judge() {
				this.bbb = "#50d8be";
			},
			lose() {
				if (!this.accounts.trim()) {
					this.bbb = "red";
					// var users = uni.getStorageSync("users");
					// console.log(users);
				} else {
					this.val1 = true;
				}
			},
			loseone() {
				if (!this.accountsone.trim()) {
					this.ccc = "red";
				} else {
					this.val2 = true;
				}
			},
			clicked() {
				this.isclick = !this.isclick;
				this.sss = this.isclick ? "#0b84ff" : "#f0f0f0";
			},
			tosubmit() {
          
		if (!this.accountsthree.trim()) {
			this.title1 = "请输入需要绑定得账户手机号";
			this.show = true;
		} else {
			this.show = false;
			this.$axios({
				url: 'http://192.168.168.161:8080/user/register',
				method: "POST",
				data: {
					account: this.accounts.trim(),
					password: this.accountsone.trim(),
					phone: this.accountsthree.trim()
				}
			}).then((parameter) => {                 
			    if(parameter.data.code===0){               //请求成功之后样式设置
					 this.title1 = "注册成功";
					 this.show = true;
					 var obj={};
					 obj.phone=parameter.data.data.phone;
					 obj.account=parameter.data.data.account;
					 getApp().globalData.loginattribute=obj;
					 // getApp().globalData.loginattribute.phone=parameter.data.data.phone;//将用户账号、手机号进行存储；
					 // getApp().globalData.loginattribute.account=parameter.data.data.account;
					 
					 setTimeout(function(){
						 uni.navigateTo({
						 	url:"./login"
						 })
					 },2000)
				}else{
					this.title1=parameter.data.msg;
					this.show=true;
				}
					
			})
		}
			},

		}
	}
</script>

<style lang="scss">
	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
	}

	.login {
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
			height: 80rpx;
			background-color: #50d8be;

			image {
				height: 45rpx;
				width: 45rpx;
				margin-top: 15rpx;
			}

			text {
				margin: 15rpx 0 0 290rpx;
				font-size: 35rpx;
				font-weight: bold;
				color: white;
			}
		}
	}

	.logo {
		margin-top: 150rpx;
		width: 100%;
		height: 200rpx;

		image {
			width: 200rpx;
			height: 200rpx;

		}
	}

	.famousremarks {
		display: flex;
		width: 60%;
		height: 60rpx;
		justify-content: space-around;
		align-items: center;

		text {
			font-style: oblique;
			font-weight: bold;

		}
	}

	.inputsr {
		margin-top: 30rpx;
		height: 300rpx;
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;

		.inputone {
			height: 100rpx;
			width: 70%;
			border: 1px solid #50d8be;

			input {
				height: 100%;
				width: 100%;
			}
		}

		.inputtwo {
			height: 100rpx;
			width: 70%;
			border: 1px solid #50d8be;

			input {
				height: 100%;
				width: 100%;
			}
		}
		.inputthree {
			height: 100rpx;
			width: 70%;
			border: 1px solid #50d8be;
		
			input {
				height: 100%;
				width: 100%;
			}
		}

	}

	.consult {
		display: flex;
		padding-left: 115rpx;
		align-items: center;
		margin: 40rpx 0;

		.checkbox {
			background-color: #f0f0f0;
			width: 45rpx;
			height: 45rpx;
			border-radius: 50%;
			margin-right: 25rpx;
			background: url(../../static/login/1.png) no-repeat center center;
			background-size: 60%;
		}

		text {
			font-size: 22rpx;
		}
	}

	.protocol {
		width: 94%;
		box-sizing: border-box;
		margin: 0 3%;
		height: 105rpx;
		height: 105rpx;

		.btn {
			width: 90%;
			height: 105rpx;
			border-radius: 52rpx;
		}
	}
</style>
