<script>
    export default {
        name: 'SingleBigCard',
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
    <div class="bigCards d-flex flex-wrap">
        <div class="my-card" v-for="n in (card.section.length)">
            <div class="links">
                <img :src='getCardImg(card.img[n-1])' alt="Product Image">
                <div class="sale" v-if="card.discount[n-1] !== ''">
                    <p>Sale!</p>
                </div>
                <div class="back text-center ">
                    <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><br>
                    <a href="#">ADD TO CART </a>/
                    <a href="#"> QUICK VIEW</a>
                </div>
            </div>
            <p class="m-0">{{card.section[n-1]}}</p>
            <p class="m-0 price"><span>{{card.discount[n-1]}}</span> {{card.price[n-1]}}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .bigCards{
        text-align: center;
        font-size: 22px;
        margin: auto;

        .my-card{
            position: relative;
            margin: 48px 0;
            width: calc(100% / 3 - 16px);
        }
        .my-card:nth-child(2){
            margin: 48px 24px 48px 24px;
        }
        .my-card:nth-child(5){
            margin: 48px 24px 48px 24px;
        }
        p{
            font-size: 22px;
            cursor: default;
            padding-top: 40px;
            &:hover{
                color: $textGreen;
            }
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
                transition: all 0.5s ease-in-out;
            }
            img{
                width: 100%;
            }
            .sale{
                position: absolute;
                top: 0;
                background-color: $bgGreen;
                color: $textColor;
                border-radius: 50%;
                height: 50px;
                aspect-ratio: 1;
                margin: 1rem;
                p{
                    font-size: 17px;
                    transform: translate(0, -45%);
                }
            }
            .back{
                transition: all 0.5s ease-in-out;
                opacity: 0;
                height: 100%;
                width: 100%;
                background-color: rgba(147, 99, 27, 0.5);
                position: absolute;
                top: 50%;
                transform: translate(0, -50%);
                color: $textColor;
                font-size: 12px;
                i{
                    margin-top: 45%;
                    margin-bottom: 15px;
                    font-size: 17px
                }
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
</style>
