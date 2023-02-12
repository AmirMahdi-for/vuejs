<template>
    <div>
        <user></user>
        <hr>
        <FlexBox></FlexBox>
        <hr>
        <h2>THIS IS App.vue</h2>

    </div>
</template>

<script>

// eslint-disable-next-line no-unused-vars
import user from './components/UserPro.vue';
import FlexBox from './components/FlexBox.vue'

export default {
    components : {
        user,
        FlexBox,
    },
}
</script>

<style>

</style>
