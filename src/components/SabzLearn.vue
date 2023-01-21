<template>
    <div>
        <p>Counter : {{ counter }}</p>
        <button @click="addCounter"> Add to Counter </button>
        <button @click="minesCounter"> mines to Counter </button>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                counter : 0,
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