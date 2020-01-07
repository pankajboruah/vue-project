<template>
    <div class="component child">
        <h1>You may edit the user here.</h1>
        <p>Edit me!</p>
        <p>User Age: {{ userAge }}</p>
        <button @click="updateAge">Edit Age</button>
    </div>
</template>

<script>
export default {
    props:[
        'userAge'
    ],
    methods:{
        updateAge(){
            this.userAge = 30;
            this.$emit("ageWasUpdated", this.userAge)
        }
    }
}
</script>

<style scoped>
    .child {
        background-color: lightgreen;
    }
</style>