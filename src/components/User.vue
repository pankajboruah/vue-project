<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I am an awesome user</p>
        <button @click="changeName">Change My Name</button>
        <p>My name is {{ name }}</p>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <UserDetail 
                :name="name" 
                @nameWasReset="name = $event" 
                :resetFn="resetName" 
                :userAge="age"
                ></UserDetail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <UserEdit 
                :userAge="age"
                @ageWasUpdated="age = $event"
                ></UserEdit>
            </div>
        </div>
    </div>
</template>

<script>
import UserDetail from "./UserDetail"
import UserEdit from "./UserEdit"
export default {
    name: 'User',
    components: {
        UserDetail,
        UserEdit
    },
    data: function(){
        return({
            name: 'max',
            age: 27
        })
    },
    methods: {
        changeName(){
            this.name='anna'
        },
        resetName(){
            this.name='pankaj'
        }
    }
}
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>