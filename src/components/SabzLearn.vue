<template>
    <div>
        <p>Counter : {{ counter }}</p>
        <button @click="addCounter"> Add to Counter </button>
        <button @click="minesCounter"> mines to Counter </button><br>
        <a :href="link">ZZZZZZZZ</a>
        <div v-html="title"></div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                counter : 0,
                link : "http://google.com",
                title : "<h1>Google</h1>"
            }
        },
        methods : {
            addCounter : function() {
                this.counter++;
            },
            minesCounter : function() {
                if(this.counter == 0){
                    alert("can not mines to counter");
                }
                else{
                    this.counter--;
                }
            }
        }
    }
</script>
    
<style>

</style>