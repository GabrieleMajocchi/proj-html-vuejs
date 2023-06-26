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
            <p class="fw-bold">FIND THE BEST ANIMAL SUPPLIES</p>
            <h1 class="fw-bold">We know animals are a <br> 
            part of your family, let us <br>
            help take care of them.</h1>
            <a href="#">Learn more about us</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixing.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .firstSection{
        color: $textColor;
        background-image: url('../../assets/img/banner-1.jpg');
        height: 790px;
        background-position: center;
        .my-container{
        width: 65%;
        margin: auto;
            h1{
                margin-bottom: 60px;
            }
            a{
                @include buttonGreen()
            }
        }
    }
</style>
