<template>
    <main class="main">
        <div class="container">

            <section class="works">

                <h5 class="works__text">HOW IT WORK</h5>

                <h2 class="works__title">
                    There Simple Step To Started Working Process
                </h2>
                
                <div class="works-content">

                        <div class="works-content__items">
                            <h6 class="works-content__title"><b>Research Project</b></h6>
                            <p class="works-content__text">
                                There are many variations of passages of lorem ipsum available
                            </p>
                        </div>

                        <div class="works-content__items">
                            <h6 class="works-content__title"><b>Goals</b></h6>
                            <p class="works-content__text">
                                There are many variations of passages of lorem ipsum available
                            </p>
                        </div>

                        <div class="works-content__items">
                            <h6 class="works-content__title"><b>Result</b></h6>
                            <p class="works-content__text">
                                There are many variations of passages of lorem ipsum available
                            </p>
                        </div>

                </div>

                <div class="works-content__img">
                    <img :src="require('/public/images/main-img.svg')" alt="" class="works-img">
                </div>

            </section>

        </div>

        <section class="person-comments">

            <div class="container">
                <h2 class="person-comments__title">
                    <b>You are in a good hand</b>
                </h2>
    
                <p class="person-comments__text">
                    There are many variations of passages of lorem ipsum available, but the majority have suffered.
                </p>

                <div class="comments-container">
                    <div class="comments">
                        <div class="comment">
                            <div class="comment__content">
                                <p class="comment__body">
                                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam accusantium nulla eaque ut cumque nesciunt id velit.
                                     Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam accusantium nulla eaque ut cumque nesciunt id velit.
                                </p>
                            </div>
                            <div class="comment__info">
                                <img :src="require('/public/images/person-1.png')" alt="" class="comment__img">
                                <p class="comment__person">Martin Jones, Product Manager</p>
                            </div>
                        </div>
    
                        <div class="comment">
                            <div class="comment__content">
                                <p class="comment__body">
                                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam accusantium nulla eaque ut cumque nesciunt id velit.
                                     Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam accusantium nulla eaque ut cumque nesciunt id velit.
                                </p>
                            </div>
                            <div class="comment__info">
                                <img :src="require('/public/images/person-2.png')" alt="" class="comment__img">
                                <p class="comment__person">Martin Jones, Product Manager</p>
                            </div>
                        </div>
    
                        <div class="comment">
                            <div class="comment__content">
                                <p class="comment__body">
                                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam accusantium nulla eaque ut cumque nesciunt id velit.
                                     Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam accusantium nulla eaque ut cumque nesciunt id velit.
                                </p>
                            </div>
                            <div class="comment__info">
                                <img :src="require('/public/images/person-3.png')" alt="" class="comment__img">
                                <p class="comment__person">Martin Jones, Product Manager</p>
                            </div>
                        </div>
                    </div>
                    <div class="companies">
                        <img :src="require('/public/images/logo-1.svg')" alt="LoGo" class="companies__img">
                        <img :src="require('/public/images/logo-2.svg')" alt="LoGo" class="companies__img">
                        <img :src="require('/public/images/logo-3.svg')" alt="LoGo" class="companies__img">
                        <img :src="require('/public/images/logo-4.svg')" alt="LoGo" class="companies__img">
                        <img :src="require('/public/images/logo-5.svg')" alt="LoGo" class="companies__img">
                    </div>
                </div>
            </div>
        </section>
        
    </main>
</template>

<script>

</script>

<style>
    /* ------------person comments section --------------*/
    .person-comments{
        background-color: #2f5bea;
        text-align: center;
        padding: 2rem 0;
    }

    .comments{
        display: flex;
        justify-content: space-between;
        
    }

    .comment{
        background-color: #fff;
        border-radius: 0.5rem;
        margin: 1rem;
        flex-basis: 20rem;
        min-height: 18rem;
        
    }

    .comments_container{
        max-width: 65rem;
        margin: 3.5rem;
    }

    .comment__body {
        font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        color: #7e8085;
        line-height: 1.5rem;
        margin: 0;
    }

    .comment__content{
        text-align: left;
        padding: 1.2rem;
    }

    .companies{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .companies__img{
        display: block;
        margin: 2rem;
    }

    .comment__info{
        display: flex;
        border-top: 1px solid #e8ebef;
        padding: 1.2rem;
        align-items: center;
    }

    .comment__person {
        color: #000;
        margin-left: 0.5rem;
        margin-top: 15px;
    }

    .person-comments__title{
        color: #fff;
    }

    .person-comments__text{
        color: #fff;
    }

    /* ----------start main------------- */
    .works{
        text-align: center;
        margin-top: 5rem;
        margin-bottom: 5rem;
    }

    .works-content{
        margin-top: 4rem;
        display: flex;
    }

    .works-content__items{
        margin: 0 5px;
        
    }

    .works-content__title{
        color: #081d43;
    }
    .works-content__text{
        color: #6c7890;
    }

    .works__text{
        color: #6c7890;
        margin-bottom: 0;
    }

    .works__title{
        color: #081d43;
        margin-top: 0.8rem;
    }

    
</style>