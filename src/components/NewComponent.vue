<template>
	<div class="new-component">
		<h1> I am the new component </h1>
		<p>
			The price is {{ price }} SEK.
		</p>
		<button v-on:click="handleClick"> Click me </button>
	</div>
	<!-- <p>
		Man ska bara ha ett element direkt i en template
	</p> -->
</template>

<script>
export default {
	// Lägg till data, computed, methods, props vid behov
	props: ['price'],
	// det blir som om vi hade en data property "price"

	methods: {
		handleClick() {
			// Tips för felsökning: ta reda på om koden körs
			console.log('NewComponent: handleClick');

			const data = { message: 'Success!' }
			this.$emit('innerClick', data)
		}
	}
}

</script>

<style scoped>
.new-component {
	border: 1px solid gray;
	padding: 1em;
	margin: 1em;
	border-radius: 1em;
}
h1 {
	color: hotpink;
}
</style>
