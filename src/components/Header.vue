<template>
    <header>
        <h1>{{title}}</h1>
        <div class="btn">
            <Button v-on:click="onclick()" text="Add" color="green"/>
        </div>
    </header>
</template>

<script>
import Button from "./Button.vue"

export default {
    name: 'Header',
    props: {
        title: {
            type: String,
            default: "Hello World",
        },
    },
    components: {
        Button
    },
    methods: {
        onclick(){
            console.log('click')
        }
    }
}
</script>

<style scoped>
    header{
        display: flex;
        flex-direction: column;
    }
</style>