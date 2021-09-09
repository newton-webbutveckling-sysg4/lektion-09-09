<template>
	<div>
		Värdet är: {{ count }} <br />
		<button v-on:click="increase"> +1 </button>
		<button v-on:click="decrease"> -1 </button>
		<button v-on:click="reset"> Återställ </button>
	</div>
</template>

<script>
export default {
	data: () => ({
		count: 10
	}),
	methods: {
		increase() {
			this.count += 1
		},
		decrease() {
			this.count -= 1
		},
		reset() {
			this.count = 10
		}
	}
}
</script>

<style scoped>
div {
	margin: 0.6em;
}
</style>
