<script>
    export default {
        name: 'TopHeader',
        data() {
            return {
            
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <div class="topHeader d-flex justify-content-between align-items-center m-auto">
        <img src="../../assets/img/dark-pet-logo.png" alt="Avada Pet Supplies Logo">
        <div class="searchBar">
            <i class="fa-solid fa-magnifying-glass"></i>
            <input type="text" placeholder="Search..">
        </div>
        <p><span class="fw-bold">Questions?</span> Call us : 1.800.123.4567</p>
        <div class="userIcons">
            <i class="fa-solid fa-cart-shopping"></i>
            <i class="fa-regular fa-user"></i>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/variables.scss' as *;

    .topHeader{
        width: 65%;
        padding: 1rem 0;
        img{
            height: 36px;
        }
        .searchBar{
            background-color: $bgGrey;
            padding: 12px 18px;
            border-radius: 30px;
            i{
                font-size: 15px;
                cursor: pointer;
            }
            input{
                border: none;
                background-color: $bgGrey;
                padding-left: 12px;
                width: 300px;
            }
        }
        .userIcons{
            i{
                margin-right: 12px;
                font-size: 20px;
            }
        }
    }
</style>
