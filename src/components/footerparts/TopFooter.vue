<script>
    export default {
        name: 'TopFooter',
        data() {
            return {
                links: [{name: 'Shop by brand', link: ['Bed', 'Food', 'Toys', 'Transport']},
                        {name: 'Useful links', link: ['My account', 'Orders', 'Checkout', 'Cart']}
                    ],
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <div class="topFooter d-flex m-auto justify-content-between">
        <!-- ---Left part with brand logo and info--- -->
        <div class="info">
            <img src="../../assets/img/mobile-light-pet-logo-2x.png" alt="Avada Pet Supplies Logo">
            <p class="m-0">1234 Avada Avenue Avadaville</p>
            <p class="m-0">info@your-company.com</p>
            <p class="m-0">Call us: (1) 234 5678</p>
        </div>
        <!-- ---Center parts with links--- -->
        <div class="links" v-for="section in links">
            <h1>{{section.name}}</h1>
            <ul class="p-0">
                <li v-for="element in section.link"><a href="#">{{element}}</a></li>
            </ul>
        </div>
        <!-- ---Right part with subscribe to newsletter tab--- -->
        <div class="newsletter">
            <h1>Subscribe to our newsletter</h1>
            <input type="text" placeholder="Insert your email..">
            <a href="#">Subscribe</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../../styles/partials/mixins.scss' as *;
    @use '../../styles/partials/variables.scss' as *;

    .topFooter{
        width: 65%;
        color: $textColor;
        border-bottom: 2px solid $textGreen;
        padding: 120px 0 60px 0;
        .info{
            img{
                width: 75%;
                margin-bottom: 35px;
                margin-top: 10px;
            }
            p{
                font-size: 17px;
            }
        }
        .info, .links, .newsletter{
            width: calc(100% / 4 - 50px);
        }
        h1{
            font-size: 24px;
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            margin-top: 10px;
        }
        .links{
            ul{
                list-style: none;
                li{
                    cursor: pointer;
                    margin: 20px 0;
                }
                li:hover a{
                    color: lightgray;
                }
            }
            a{
                text-decoration: none;
                color: $textColor;
                font-size: 16px;
            }
            h1{
                margin-bottom: 40px;
            }
        }
        .newsletter{
            background-image: url('../../assets/img/newsletterbg.png');
            border-radius: 5px;
            padding: 20px 35px 45px 35px;
            width: 300px;
            h1{
                font-size: 22px;
            }
            input{
                border: none;
                background-color: $bgAlmond;
                padding: 18px 16px;
                border-radius: 30px;
                width: 100%;
                margin-right: 20px;
                font-size: 16px;
                margin-top: 30px;
                margin-bottom: 45px;
            }
            a{
                font-size: 18px;
                text-decoration: none;
                font-weight: 500;
                color: $textColor;
                background-color: $bgGreen;
                padding: 18px 71px;
                border-radius: 30px;
                transition: all 0.3s;
                    &:hover{
                        color: $textColor;
                        background-color: $bgDarkGreen;
                    }
            }
        }
    }
</style>
