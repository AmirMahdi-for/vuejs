<template>
    <div class="container">
        <div class="search">search</div>
        <div class="home">home</div>
        <div class="login">login</div>
    </div>
</template>

<script>

</script>

<style scoped>
    body{
        font-size: 16px;
    }

    .container{
        /* FLEX STYLE  */
        display: flex;
        flex-direction: row;


        /* CSS STYLE  */
        background-color: #8395a7;
        border: 4px solid #222f3e;
        height: 400px;
    }

    .container > div{
        font-size: 1.4em;
        color: white;
        padding: 10px;
        text-align: center;
        
    }

    .search{
        /* FLEX STYLE  */
        flex: 1;
        align-self: flex-start;
        /* CSS STYLE  */
        background-color: #01a3a4;
    }

    .home{
        /* FLEX STYLE  */
        flex: 3;
        align-self: center;
        /* CSS STYLE  */    
        background-color: #ff9f43;
    }

    .login{
        /* FLEX STYLE  */
        flex: 1;
        align-self: flex-end;
        /* CSS STYLE  */
        background-color: #f368e0;
    }

</style>