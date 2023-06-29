<script>
    export default {
        name: 'FirstSection',
        data() {
            return {
                
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <div class="firstSection d-flex align-items-center">
        <div class="my-container">
            <p class="fw-semibold">FIND THE BEST ANIMAL SUPPLIES</p>
            <h1 class="fw-normal">We know animals are a <br> 
            part of your family, let us <br>
            help take care of them.</h1>
            <a href="#" class="fw-medium">Learn more about us</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .firstSection{
        color: $textColor;
        background-image: url('../../assets/img/banner-1.jpg');
        height: 790px;
        background-position: center;
        background-size: cover;
        .my-container{
        width: 65%;
        margin: auto;
            p{
                font-size: 14px;
                line-height: 15px;
                letter-spacing: 2px;
            }
            h1{
                margin-bottom: 60px;
                font-size: 52px;
                line-height: 70px;
                font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            }
            a{
                font-size: 14px;
                @include buttonGreen()
            }
        }
    }
</style>
