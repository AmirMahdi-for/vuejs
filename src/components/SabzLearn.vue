<template>
    <div>
        GB: <input type="text" v-model="GB">
        MB: <input type="text" v-model="MB">
    </div>
</template>

<script>
    export default {
        data() {
            return {
                GB : null,
                MB : null,
            }
        },
        watch: {
            GB: function (val) {
                this.MB = val * 1024;
            },
            MB: function () {
            
            }
        }
    }
</script>
    
<style>

</style>
<!-- END -->