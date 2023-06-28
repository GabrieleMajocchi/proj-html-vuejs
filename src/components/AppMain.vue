<script>
import FirstSection from './mainparts/FirstSection.vue';
import PromoBanner from './mainparts/PromoBanner.vue';
import SingleCard from './mainparts/SingleCard.vue';
import SingleFoodtype from './mainparts/SingleFoodtype.vue';
import SingleTestimonials from './mainparts/SingleTestimonials.vue';
import NewsletterSection from './mainparts/NewsletterSection.vue';
import BigPics from './mainparts/BigPics.vue';
import SingleBigCard from './mainparts/SingleBigCard.vue';
    export default {
        name: 'AppMain',
        components: {
            FirstSection,
            PromoBanner,
            SingleCard,
            SingleFoodtype,
            SingleTestimonials,
            NewsletterSection,
            BigPics,
            SingleBigCard,
        },
        data() {
            return {
                arrayCard: [{name: 'browse', section: ['Bed (1)', 'Food (6)', 'Toys (6)', 'Transport (7)'], img: ['product-9.jpg', 'product-3.jpg', 'product-2.jpg', 'product-4.jpg']}, 
                            {name: 'bestsellers', section: ['Transport cage', 'Dog leash', 'Animal transport cage', 'Colorful cat leash'], price: ['$25.00', '$25.00', '$25.00', '$12.00'], img: ['product-21.jpg', 'product-20.jpg', 'product-16.jpg', 'product-11.jpg'], discount: ['', '', '$35.00', '']},
                            {name: 'articles', section: ['How to ‘loose leash walk’ your dog', 'Stop cats from scratching furniture', 'Where to buy the best pet food', 'Proper care for your pet toys'], date: ['April 21st, 2020', 'April 19st, 2020', 'April 18st, 2020', 'April 17st, 2020'], img: ['blog-1.jpg', 'blog-2.jpg', 'blog-3.jpg', 'blog-4.jpg']}
                        ],
                
                foodlist: [{name: 'Kibble', type: 'Dry dog food', img: 'food-transparent-18.png', section: 'dry food'},
                            {name: 'Moist', type: 'Canned dog food', img: 'food-transparent-17.png', section: 'moist food'},
                            {name: 'Frozen', type: 'Freeze-Dried dog food', img: 'food-transparent-16.png', section: 'frozen food'}
                        ],

                testimonials: [{name: 'Lisa Smith, ThemeFusion', review: 'Auctor est habitasse amet nunc, interdum vel mattis sodales cras. Ut nulla quis nunc, tincidunt eu. Eu.', img: 'avatar-3.jpg'},
                                {name: 'Melissa Green, ThemeFusion', review: 'Donec sollicitudin molestie malesuada. Vivamus suscipit tortor eget felis porttitor volutpat vestibulum ac diam sit.', img: 'avatar-1.jpg'},
                                {name: 'Sam Lewis, ThemeFusion', review: 'Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem. Proin eget tortor risus vestibulum ante ipsum.', img: 'avatar-4.jpg'},
                        ],

                bigPics: [{name: 'FIND THE BEST ANIMAL SUPPLIES', section: 'Popular accessories',  img: 'banner-8-2x.jpg', button: 'View all toys accessories'},
                        {name: 'FIND THE BEST FOOD', section: 'New food arrival', img: 'banner-9-2x.jpg', button: 'View all food products'}
                    ],

                newProducts: {section: ['Colored pet bed', 'Colorful ball set', 'Dog bone', 'Animal transport bag', 'Animal transport cage', 'Closable cat litter'], 
                            price: ['$25.00', '$29.00', '$18.00', '$29.00', '$35.00', '$16.00'], 
                            img: ['product-8.jpg', 'product-2.jpg', 'product-3.jpg', 'product-4.jpg', 'product-5.jpg', 'product-10.jpg'], 
                            discount: ['', '', '$29.00', '', '', '']
                        },
            }
        },
        methods: {
            
        },
    }
</script>

<template>
    <main>
        <!-- ---First section, slogan--- -->
        <FirstSection/>
        <!-- ---Promo banner--- -->
        <PromoBanner/>
        <!-- ---Browse by category--- -->
        <div class="browse d-flex flex-column">
            <h1 class="m-auto fw-normal">Browse by category</h1>
            <p class="m-auto text-center">Augue purus et, tincidunt condimentum mauris. At nibh rutrum mi in. Nisi, vitae interdum eleifend dui, consequat nulla rhoncus dictum. Viverra.</p>
            <SingleCard :card="arrayCard[0]"/>
        </div>
        <!-- ---Food type card--- -->
        <SingleFoodtype :foodlist="foodlist"/>
        <!-- ---New arrivals weekly--- -->
        <div class="newArrivals">
            <p class="fw-semibold">FIND THE BEST ANIMAL SUPPLIES</p>
            <h1 class="fw-normal">New arrivals weekly</h1>
            <a href="#" class="fw-medium">Learn more about us</a>
        </div>
        <!-- ---All-time best sellers--- -->
        <div class="bestSeller">
            <div class="upperpart d-flex justify-content-between">
                <div class="left">
                    <p>All-Time best sellers</p>
                    <h1 class="fw-normal">Items everyone loves</h1>
                </div>
                <a href="#" class="fw-medium">View all products</a>
            </div>
            <SingleCard :card="arrayCard[1]"/>
        </div>
        <!-- ---Users testimonials--- -->
        <div class="testimonials">
            <h1 class="fw-normal">Users testimonials</h1>
            <SingleTestimonials :testimonials="testimonials"/>
        </div>
        <!-- ---Newsletter--- -->
        <div class="newsletter">
            <NewsletterSection/>
        </div>
        <!-- ---Tips and tricks--- -->
        <div class="tips text-center">
            <h1 class="fw-normal">Get the best tips & tricks</h1>
            <p>Recent articles</p>
            <SingleCard :card="arrayCard[2]"/>
            <a href="#" class="fw-medium">Read all articles</a>
        </div>
        <!-- ---Big pic and infos--- -->
        <div class="bigPic">
            <div class="pics d-flex">
                <BigPics v-for="bigpic in bigPics" :bigPic="bigpic"/>
            </div>
            <div class="bottom d-flex justify-content-center align-items-center">
                <div>
                    <i class="fa-solid fa-truck"></i>
                    <p>Free worldwide deliveries</p>
                </div>
                <div>
                    <i class="fa-regular fa-map"></i>
                    <p>Find stores near you</p>
                </div>
                <div>
                    <i class="fa-solid fa-dollar-sign"></i>
                    <p>Best prices guarranteed</p>
                </div>
                <div>
                    <i class="fa-regular fa-credit-card"></i>
                    <p>All credit card accepted</p>
                </div>
            </div>
        </div>
        <!-- ---New products arrival--- -->
        <div class="newProducts text-center">
            <h1>New products arrival</h1>
            <p>Latest products</p>
            <SingleBigCard :card="newProducts"/>
        </div>
    </main>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixins.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    .browse{
        margin-top: 100px;
        h1{
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            font-size: 34px;
            line-height: 46px;
            padding-bottom: 15px;
        }
        p{
            width: 35%;
            font-size: 17px;
            line-height: 31px;
        }
    }

    .newArrivals{
        background-image: url('../assets/img/banner-3-2x-scaled.jpg');
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        height: 515px;
        color: $textColor;
        text-align: center;
        width: 65%;
        margin: auto;
        padding-top: 150px;
        margin-top: 100px;
        h1{
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            margin-bottom: 3rem;
            font-size: 50px;
        }
        p{
            font-size: 14px;
            letter-spacing: 2px;
        }
        a{
            font-size: 14px;
            @include buttonGreen(0)
        }
    }

    .bestSeller{
        padding-top: 100px;
        width: 65%;
        margin: auto;
        p{
            font-size: 20px;
            color: $textGreen;
        }
        h1{
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            font-size: 34px;
        }
        a{
            height: fit-content;
            font-size: 14px;
            @include buttonGreenDark(0)
        }
    }

    .testimonials{
        margin-top: 50px;
        background-image: url('../assets/img/testimonialsbg.png');
        height: 700px;
        h1{
            font-size: 34px;
            text-align: center;
            color: $textColor;
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
            padding-top: 130px;
        }
    }

    .newsletter{
        margin-top: -100px;
    }
    .tips{
        margin-top: 100px;
        h1{
            font-size: 34px;
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
        }
        p{
            color: $textGreen;
            font-size: 20px;
            margin-top: 20px;
        }
        a{
            font-size: 14px;
            @include buttonGreenDark(0)
        }
    }

    .bigPic{
        margin-top: 50px;
        .bottom{
            background-image: url('../assets/img/testimonialsbg.png');
            height: 330px;
            text-align: center;
            div{
                margin: 0 70px 0 70px;
            }
            i{
                color: $textColor;
                font-size: 50px;
            }
            p{
                margin-top: 20px;
                color: lightgray;
                font-size: 17px;
            }
        }
    }

    .newProducts{
        width: 65%;
        margin: auto;
        margin-top: 100px;
        h1{
            font-size: 34px;
            font-family: 'Trocchi', Arial, Helvetica, sans-serif;
        }
        p{
            margin-top: 20px;
            color: $textGreen;
            font-size: 20px;
        }
    }
</style>
