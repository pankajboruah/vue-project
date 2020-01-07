<template>
    <div>
        <p>hi</p>
        <p>{{ quote }}</p>
        <slot></slot>
    </div>
</template>

<script>
export default {
    props:{
        quote: String
    }
}
</script>

<style lang="stylus">

</style>