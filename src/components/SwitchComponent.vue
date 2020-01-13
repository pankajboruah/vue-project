<template>
    <div>
        <div id="on" :class="{active: value}" @click= "switched(true)">
            ON
        </div>
        <div id="off" :class="{active: !value}" @click= "switched(false)">
            OFF
        </div>
    </div>
</template>

<script>
export default {
    props: ['value'],
    methods:{
        switched(status){
            this.$emit('input', status)
        }
    }

}
</script>

<style scoped>
    #on, #off{
        width: 40px;
        height: 20px;
        background-color: lightgrey;
        padding: 2px;
        margin: 10px -2px;
        display: inline-block;
        box-sizing: content-box;
        cursor: pointer;
        text-align: center;
    }
    #on:hover, #on.active{
        background-color: lightgreen;
    }

    #off:hover, #off.active{
        background-color: lightcoral;
    }
</style>