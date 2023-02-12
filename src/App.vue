<template>
    <div>
        <HeaderContent></HeaderContent>
        <MainContent></MainContent>
        <hr>
        <FlexBox></FlexBox>
        <hr>
        <h2>THIS IS App.vue</h2>

    </div>
</template>

<script>

// eslint-disable-next-line no-unused-vars
import HeaderContent from './components/HeaderContent.vue';
import MainContent from './components/MainContent.vue';
import FlexBox from './components/FlexBox.vue'

export default {
    components : {
        HeaderContent,
        MainContent,
        FlexBox,
    },
}
</script>

<style>

</style>
