<template>
	<div class="block" v-if="showBlock" @click="stopTimer">
		<h3>Click me</h3>
	</div>
</template>

<script>
export default {
	props: ['delay'],
	data() {
		return {
			showBlock: false,
			timer: null,
			reactionTime: 0,
		}
	},
	mounted() {
		console.log('Component mounted')
		setTimeout(() => {
			this.showBlock = true
			this.startTimer()
		}, this.delay)
	},
	methods: {
		startTimer() {
			this.timer = setInterval(() => {
				this.reactionTime += 10
			}, 10)
		},
		stopTimer() {
			clearInterval(this.timer)
			this.$emit('end', this.reactionTime)
		},
	},
}
</script>

<style>
.block {
	cursor: pointer;
	width: 400px;
	border-radius: 20px;
	background: mediumseagreen;
	padding: 100px 0;
	margin: 40px auto;
}

.block h3 {
	color: white;
	text-align: center;
}
</style>
