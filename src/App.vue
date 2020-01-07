<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <Quote quote="This is a new quote">
                    <h1>Quote 1</h1>
                    <p>Another quote</p>
                </Quote>
                <button @click="selectedApp='Blue'">Use Blue</button>
                <button @click="selectedApp='Green'">Use Green</button>
                <button @click="selectedApp='Red'">Use Red</button>
                <component :is="selectedApp"><p>This is a new quote</p></component>
                <!-- <Blue><p>This is a new quote</p></Blue>
                <Green><p>This is a new quote</p></Green>
                <Red><p>This is a new quote</p></Red> -->
                <app-user></app-user>
            </div>
        </div>
    </div>
</template>

<script>
    import User from './components/User.vue';
    import Quote from './components/Quote.vue'
    import Red from './components/Red.vue'
    import Blue from './components/Blue.vue'
    import Green from './components/Green.vue'
    export default {
        data:function(){
            return{
                selectedApp: 'Blue'
            }
        },
        components: {
            appUser: User,
            Quote,
            Red,
            Green,
            Blue
        }
    }
</script>

<style>
    div.component {
        border: 1px solid black;
        padding: 30px;
    }
</style>
