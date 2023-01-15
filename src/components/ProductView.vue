<template>
    <div>
        {{ message }}
        <br>
        {{ my_data.name }}
        <br>
        <a :href="my_data.web_url">THIS IS GOOGLE</a>
    </div>
</template>

<script>
    export default {
        data()  {
            return {
                message : 'HelloVueJs',

                my_data : {
                    name : 'amir mahdi',
                    age : '20',
                    web_url : 'http:///google.com',
                }
            }
        },
    }
</script>

<style>

</style>