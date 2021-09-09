<template>
<div>
	<span v-show="showText" v-on:click="handleClick"> {{ text }} </span>
	<input v-show="!showText" type="text"
		v-model="text2"
		v-on:blur="handleBlur" />
</div>
<!-- {{ text2 }} -->
<!-- v-bind:value="text" -->
</template>

<script>
export default {
	props: ['text'],
	data: () => ({
		showText: true,
		text2: ''
	}),
	methods: {
		handleClick() {
			// Användaren klickar på span-elementet
			this.showText = false
		},
		handleBlur() {
			// Användaren lämnar input-fältet (tappar fokus)
			console.log('EditableText: handleBlur');
			this.$emit('update', this.text2)
			this.showText = true
		}
	}
}
</script>

<style scoped>

</style>
