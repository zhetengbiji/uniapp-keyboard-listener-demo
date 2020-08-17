<template>
	<view class="content">
		<keyboard-listener @keyup="onKeyup" @keydown="onKeydown"></keyboard-listener>
		<view>事件信息：</view>
		<view class="log" v-for="(item,index) in logs" :key="index">{{item}}</view>
	</view>
</template>

<script>
	import keyboardListener from 'uniapp-keyboard-listener'

	export default {
		components: {
			keyboardListener
		},
		data() {
			return {
				title: 'Hello',
				logs: []
			}
		},
		onLoad() {

		},
		methods: {
			onKeyup(event) {
				this.log(event)

			},
			onKeydown(event) {
				this.log(event)
			},
			log(event) {
				console.log(event)
				this.logs.push(`event.type: ${event.type}\nevent.key: ${event.key}\nevent.code :${event.code}\nevent.keyCode :${event.keyCode}`)
			}
		}
	}
</script>

<style>
	.log {
		word-wrap: break-word;
		white-space: pre;
		border: 1px solid #999999;
		margin: 2px;
	}
</style>
