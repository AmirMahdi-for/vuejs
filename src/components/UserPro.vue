<template>

    <header class="header container">

        <section class="header-top">
                
            <div class="nav">

                <div class="nav-logo">
                    <img :src="require('/public/images/Interactive-ART.png')" alt="logo" class="nav-logo_img">
                </div>
        
                <ul class="menu">
        
                    <li class="menu_item">
                        <a href="" class="menu_link">Home</a>
                    </li>
                    <li class="menu_item">
                        <a href="" class="menu_link">About</a>
                    </li>
                    <li class="menu_item">
                        <a href="" class="menu_link">How it work</a>
                    </li>
                    <li class="menu_item">
                        <a href="" class="menu_link">Clients</a>
                    </li>
                    <li class="menu_item">
                        <a href="" class="menu_link">Portfolio</a>
                    </li>
        
                </ul>

            </div>

            <a href="" class="header_link">Contact Us</a>
        </section>

    </header>

</template>

<script>

</script>

<style>

        
    .header {

    }

    .header-top {
        display:flex;
        justify-content: space-between;
        align-items: center;
        padding: 1.5rem 0;
    }

    .nav {
        display: flex;
        align-items: center;
    }
    .nav-logo {
        margin-right: 3px;
    }

    .nav-logo_img {

    }

    .menu {
        list-style-type: none;
        padding-left: 0;
        margin: 0;
        display: flex;
    }
    .menu_item {

    }

    .menu_link {
        text-decoration: none;
        color: #081D43;
        padding: 0 1rem;
    }

    .header_link {

    }

</style>