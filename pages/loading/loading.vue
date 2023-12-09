<template>
	<view>
		1111
	</view>
</template>

<script>
	export default {
		name: 'Loading',
		data() {
			return {
				orderNo: '',
				userId: '',
				query: {}
			}
		},
		// '/pages/loading/loading?' + query + 'orderNo=' + data.orderSn + '&userId=' + getUserId()
		onLoad(options) {
			const {
				orderNo,
				userId,
				...args
			} = options
			this.orderNo = orderNo
			this.userId = userId
			this.query = args
			console.log(options)
			uni.navigateToMiniProgram({
				appId: 'wx984383bfd5405df1',
				path: 'pages/orderDetail/orderDetail?' + this.query,
				extraData: {},
				success: (res) => {
					console.log('打开成功')
				},
				fail: (err) => {
					console.log('打开失败', err)
				},
				complete: (result) => {
					setTimeout(() => {
						uni.navigateBack()
					}, 500);
				}
			})
		},
		methods: {

		}
	}
</script>

<style></style>