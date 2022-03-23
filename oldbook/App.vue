<script>
	export default {
		globalData:{
			"loginattribute":{}
		},
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	@import "uview-ui/index.scss";
	/*每个页面公共css */
body{
	background: url(static/background.png);
	background-size: 100% 100%;
	/* opacity: 0.5; */
	
	
}	

</style>
