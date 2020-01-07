<template>
    <div class="component child">
        <h1>You may view the user details here.</h1>
        <p>Many details here: </p>
        <p>User Name: {{ name }}</p>
        <p>User age: {{ userAge }}</p>
        <button @click="resetName" >Reset Name</button>
        <button @click="resetFn">Reset Name</button>
    </div>
</template>

<script>
export default {
    props: {
        name: {
            type: String
        },
        resetFn: {
            type: Function
        },
        userAge: Number
    },
    methods:{
        resetName(){
            this.name = 'max'
            this.$emit('nameWasReset', this.name)
        }
    }
}
</script>

<style scoped>
    .child {
        background-color: lightcoral;
    }
</style>