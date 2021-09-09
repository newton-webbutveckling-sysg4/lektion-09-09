<template>
    <div class="hello">
        <h1> Products </h1>
        <div>
            The lawnmower costs {{cost}} SEK. (${{costDollar}})
        </div>
        <div>
            The fruits are:
            <ul>
                <li v-for="fruit in fruits" v-bind:key="fruit">
                    {{ fruit }}
                </li>
            </ul>

            Real fruits:
            <ul>
                <li v-for="fruit in realFruits" v-bind:key="fruit">
                    {{ fruit }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    data: () => ({
        cost: 5000,
        fruits: ['banana', 'apple', 'mango', 'strawberry']
        // { name: 'banana', id: 100, type: 'fruit' }
    }),
    computed: {
        costDollar() {
            return (this.cost / 8.6).toFixed(2)
            // return Math.ceil(this.cost / 8.6 * 100) / 100
        },
        realFruits() {
            return this.fruits.filter(fruit => fruit !== 'strawberry')
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
    border: 1px solid gray;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
