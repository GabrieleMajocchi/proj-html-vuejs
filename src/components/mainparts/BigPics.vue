<script>
    export default {
        name: 'BigPics',
        props: {
            bigPic: Object,
        },
        data() {
            return {
                imgurl: '',
            }
        },
        methods: {
            getCardImg(img){
                return new URL(`../../assets/img/${img}`, import.meta.url).href;
            },

            getBackground() {
                return {
                    'background-image': 'url('+this.imgurl+')',
                    }
            },
        },
        created(){
            this.imgurl = this.getCardImg(this.bigPic.img)
        },
    }
</script>

<template>
    <div class="bigPic d-flex flex-column align-items-center justify-content-center" :style="getBackground()">
        <p class="fw-semibold">{{bigPic.name}}</p>
        <h1>{{bigPic.section}}</h1>
        <a href="#" class="fw-medium">{{bigPic.button}}</a>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .bigPic{
        width: 100%;
        height: 500px;
        background-size: cover;
        background-position: top;
        background-repeat: no-repeat;
        color: $textColor;
        transition: all 0.3s;
        &:hover{
            transition: all 0.3s;
            transform: scale(1.03);
        }
        p{
            font-size: 14px;
            letter-spacing: 2px;
        }
        h1{
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            font-size: 40px;
            margin: 25px 0 45px 0;
        }
        a{
            font-size: 14px;
            @include buttonOnlyWhite()
        }
    }
</style>
