<template>
	<p>Reaction Time: {{ score }} ms</p>
	<h3>
		Your Rank : <span>{{ rank }}</span>
	</h3>
</template>

<script>
export default {
	props: ['score'],
	data() {
		return {
			rank: null,
		}
	},
	mounted() {
		if (this.score < 250) {
			this.rank = 'Ninja Fingers'
		} else if (this.score < 400) {
			this.rank = 'Rapid Reflexes'
		} else {
			this.rank = 'Snail pace...'
		}
	},
}
</script>

<style scoped>
p {
	font-size: 1.4rem;
	color: #444;
}
h3 {
	font-size: 2rem;
	color: #333;
}
h3 span {
	color: mediumseagreen;
}
</style>
