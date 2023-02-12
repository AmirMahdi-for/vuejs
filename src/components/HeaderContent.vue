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

        <section class="header-button">
            <div class="header-content">
                <div class="header-content__left">

                    <h1 class="header-content__title">
                        <b>CREATE A NEW GENERATION WEBSITE FOR YOUR BUSINESS</b>
                    </h1>

                    <p class="header-content__text">
                        There are many valuation of passages of Lorem ipsum dolor,
                         sit amet consectetur adipisicing elit. Autem voluptas,
                         expedita aspernatur temporibus nulla blanditiis fugit,
                         natus minima nisi repudiandae praesentium tenetur accusantium.
                    </p>

                    <div class="header-content__links">
                        <a class="header-content__link"  href="">Content Us</a>
                        <a class="header-content__link" href="">See our works</a>
                    </div>

                </div>
                <div class="header-content__right">
                    <img :src="require('/public/images/header-img.svg')" alt="header-img" class="header-content__img">
                </div>
            </div>
        </section>

    </header>

</template>

<script>

</script>

<style>

    /* header top */    

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


    .menu {
        list-style-type: none;
        padding-left: 0;
        margin: 0;
        display: flex;
    }


    .menu_link {
        text-decoration: none;
        color: #081D43;
        padding: 0 1rem;
    }

    .header_link{
        background-color: #0050CB;
        padding: 0.8rem 1.5rem;
        color: #fff;
        border-radius: 0.5rem;
        text-decoration: none;
    }

    /* header button */
    .header-button{
        margin-top: 4rem;
    }

    .header-content{
        display: flex;
    }

    .header-content__left{
        flex-basis: 50%;
        align-items: center;
        margin-top: 5rem;
        margin-right: 4rem;
    }

    .header-content__right{
        flex-basis: 50%;
    }

    .header-content__img{
        width: 100%;
    }

    .header-content__title{
        color: #081D43;
        margin-bottom: 1rem;
    }

    .header-content__text{
        color: #6c7890;
    }

    .header-content__link{
        background-color: #0050CB;
        padding: 0.8rem 1.5rem;
        color: #fff;
        border-radius: 0.5rem;
        text-decoration: none;
        margin-right: 1rem;
        display: block;
        width: 10rem;
       text-align: center;
    }

    .header-content__link:nth-child(1){
        background-color: #87bc25;
    }

    .header-content__links{
        display: flex;
    }

</style>