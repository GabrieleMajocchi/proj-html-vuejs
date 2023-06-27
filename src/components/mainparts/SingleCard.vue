<script>
    export default {
        name: 'SingleCard',
        props: {
            card: Object,
        },
        data() {
            return {
                
            }
        },
        methods: {
            getCardImg(img){
                return new URL(`../../assets/img/${img}`, import.meta.url).href;
            }
        },
    }
</script>

<template>
    <!-- ---Browse section--- -->
    <div class="cardsBrowse d-flex" v-if="card.name === 'browse'">
        <div class="my-card" v-for="n in (card.section.length)">
            <img :src='getCardImg(card.img[n-1])' alt="Product Image">
            <p class="m-0">{{card.section[n-1]}}</p>
        </div>
    </div>
    <!-- ---Bestsellers section--- -->
    <div class="cardsBest d-flex" v-if="card.name === 'bestsellers'">
        <div class="my-card" v-for="n in (card.section.length)">
            <div class="links">
                <img :src='getCardImg(card.img[n-1])' alt="Product Image">
                <div class="back text-center d-flex align-items-center justify-content-center">
                    <a href="#">ADD TO CART </a>/
                    <a href="#"> QUICK VIEW</a>
                </div>
            </div>
            <p class="m-0">{{card.section[n-1]}}</p>
            <p class="m-0 price"><span>{{card.discount[n-1]}}</span> {{card.price[n-1]}}</p>
        </div>
    </div>
    <!-- ---Browse section--- -->
    <div class="cardsArticles d-flex" v-if="card.name === 'articles'">
        <div class="my-card" v-for="n in (card.section.length)">
            <div class="links">
                <img :src='getCardImg(card.img[n-1])' alt="Article Image">
                <div class="back d-flex flex-column justify-content-center p-3">
                    <a href="#">{{card.section[n-1]}}</a><br>
                    <a href="#">Tips & Tricks</a>
                </div>
            </div>
            <p class="m-0">{{card.section[n-1]}}</p>
            <p class="m-0 date">{{card.date[n-1]}}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .cardsBrowse{
        text-align: center;
        font-size: 22px;
        width: 65%;
        margin: auto;
        img{
            width: 100%;
        }
        .my-card{
            margin: 48px 12px;
        }
        .my-card:hover p{
            color: $textGreen;
        }
    }
    .cardsBest{
        text-align: center;
        font-size: 22px;
        margin: auto;
        .my-card{
            position: relative;
            margin: 48px 0;
        }
        .my-card:nth-child(2){
            margin: 48px 12px 48px 24px;
        }
        .my-card:nth-child(3){
            margin: 48px 24px 48px 12px;
        }
        .price{
            color: $textGreen;
            font-size: 13px;
            span{
                text-decoration: line-through;
            }
        }
        .links{
            position: relative;
            &:hover .back{
                opacity: 1;
                transition: all 0.3s;
            }
            img{
                width: 100%;
            }
            .back{
                transition: all 0.3s;
                opacity: 0;
                height: 100%;
                width: 100%;
                background-color: rgba(147, 99, 27, 0.5);
                position: absolute;
                top: 50%;
                transform: translate(0, -50%);
                color: $textColor;
                font-size: 12px;
                a{
                    text-decoration: none;
                    color: $textColor;
                    letter-spacing: 1px;
                    cursor: default;
                    &:hover{
                        color: lightgrey;
                    }
                }
            }
        }
    }

    .cardsArticles{
        text-align: left;
        font-size: 22px;
        margin: auto;
        width: 65%;
        .links{
            position: relative;
            &:hover .back{
                opacity: 1;
                transition: all 0.3s;
            }
            img{
                width: 100%;
            }
            .back{
                transition: all 0.3s;
                opacity: 0;
                height: 100%;
                width: 100%;
                background-color: rgba(147, 99, 27, 0.5);
                position: absolute;
                top: 50%;
                text-align: center;
                transform: translate(0, -50%);
                a{
                    text-decoration: none;
                    color: $textColor;
                    font-size: 22px;
                    &:nth-child(3){
                        margin-top: 10px;
                        font-size: 13px;
                    }
                }
            }
        }
        p{
            padding: 24px 38px 0 38px;
            &:nth-child(3){
                padding-top: 6px;
            }
        }
        .my-card{
            margin: 48px 0;
        }
        .my-card:nth-child(2){
            margin: 48px 12px 48px 24px;
        }
        .my-card:nth-child(3){
            margin: 48px 24px 48px 12px;
        }
        p:nth-child(1):hover{
            color: $textGreen;
        }
        .date{
            font-size: 13px;
        }
    }
</style>
