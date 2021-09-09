<template>
    <HelloWorld />
    <new-component v-bind:price="thePrice"
        v-on:innerClick="handleClickFromNewComponent"></new-component>

    {{ message }}
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import NewComponent from './components/NewComponent.vue'
// .    <- current directory
// ..   <- parent directory

export default {
    name: 'App',
    components: {
        HelloWorld,
        "new-component": NewComponent
    },
    data: () => ({
        thePrice: 256,
        message: 'No click recorded'
    }),
    methods: {
        handleClickFromNewComponent(data) {
            this.message = 'Click recorded, with data: ' + data.message
        }
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
