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
    <div class="cardsBrowse d-flex" v-if="card.name === 'browse'">
        <div class="my-card" v-for="n in (card.section.length)">
            <img :src='getCardImg(card.img[n-1])' alt="Product Image">
            <p class="m-0">{{card.section[n-1]}}</p>
        </div>
    </div>
    <div class="cardsBest d-flex" v-if="card.name === 'bestsellers'">
        <div class="my-card" v-for="n in (card.section.length)">
            <img :src='getCardImg(card.img[n-1])' alt="Product Image">
            <p class="m-0">{{card.section[n-1]}}</p>
            <p class="m-0 price"><span>{{card.discount[n-1]}}</span> {{card.price[n-1]}}</p>
            <div class="links">
                <a href="#">ADD TO CART</a>/
                <a href="#"> QUICK VIEW</a>
            </div>
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
        img{
            width: 100%;
            &:hover{
                outline: 170px solid rgb(147, 99, 27, 0.4) !important;
                outline-offset: -170px;
                overflow: hidden;
                position: relative;
                height: 85.9%;
                width: 100%;
            }
        }
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
            position: absolute;
            top: 45%;
            left: 1px;
            font-size: 12px;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100%;
            color: $textColor;
            opacity: 1;
            a{
                text-decoration: none;
                letter-spacing: 1px;
                color: $textColor;
                cursor: default;
                &:hover{
                    color: grey;
                }
            }
        }
    }
</style>
