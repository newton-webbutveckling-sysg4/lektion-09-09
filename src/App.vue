<template>
    <ToggleText></ToggleText>
    <div>
        Klicka för att ändra texten:
        <EditableText
            v-bind:text="editable"
            v-on:update="updatedText"></EditableText>
    </div>

    <Counter></Counter>
    <Counter></Counter>
    <Counter></Counter>

    <HelloWorld />
    <new-component v-bind:price="thePrice"
        v-on:innerClick="handleClickFromNewComponent"></new-component>

    {{ message }}
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import NewComponent from './components/NewComponent.vue'
import Counter from './components/Counter.vue'
import EditableText from './components/EditableText.vue'
import ToggleText from './components/ToggleText.vue'
// .    <- current directory
// ..   <- parent directory

export default {
    name: 'App',
    components: {
        HelloWorld,
        "new-component": NewComponent,
        Counter,
        EditableText,
        ToggleText
    },
    data: () => ({
        thePrice: 256,
        message: 'No click recorded',
        editable: 'Exempel'
    }),
    methods: {
        handleClickFromNewComponent(data) {
            this.message = 'Click recorded, with data: ' + data.message
        },
        updatedText(data) {
            console.log('App: updatedText', data);
            this.editable = data
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
