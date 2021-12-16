<template>
	<view>
		<view class="payment-content">
			<view class="payment-content-amount">
				<view class="payment-content-amount-header">
					<view>消费总额</view>
					<view style="width: 300rpx;">
						<u--input placeholder="询问服务员后输入" border="bottom" v-model="amount" clearable
							@change="changeAmount()">
						</u--input>
					</view>
				</view>
				<view class="payment-content-amount-footer">
					<view>
						<view style="font-size: 35rpx;">积分抵扣：¥200</view>
						<view style="font-size: 30rpx; color: #808080;">可用积分：¥200</view>
					</view>
					<view>
						<u-radio></u-radio>
					</view>
				</view>
			</view>
		</view>
		<view class="payment-content-operation">
			footer
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				amount: ''
			}
		},
		methods: {
			changeAmount(value) {
				console.log(this.amount)
			}
		}
	}
</script>

<style scoped>
	.payment-content {
		background-color: #555555;
		padding: 20rpx;
	}

	.payment-content-amount {
		border: 1rpx solid #000;
		border-radius: 10rpx;
		height: 200rpx;
		padding: 20rpx;
	}

	.payment-content-amount-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.payment-content-amount-footer {
		margin-top: 20rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.payment-content-operation {
		width: 100%;
		height: 200rpx;
		position: absolute;
		bottom: 0rpx;
		background-color: #555555;
	}
</style>
