<template>
    <div v-if="isMenCategory || isWomenCategory">
        <!-- loader -->
        <div class="loader" v-if="isLoading">
            <div class="spin"></div>
        </div>
        <!-- main page -->
        <div class="container">
            <span :class="{'bg-men': isMenCategory, 'bg-women': isWomenCategory}"></span>
            <div class="box">
                <img :src="dataProduct.image" alt="">
                <div class="description">
                    <h1 :class="{'title-men': isMenCategory, 'title-women': isWomenCategory}">{{ dataProduct.title }}</h1>
                    <div class="info">
                        <p class="text-netral">{{ dataProduct.category }}</p>
                        <div class="rating">
                            <p class="text-netral">{{ dataProduct.rating.rate }}/5</p>
                            <div class="rating-dotted">
                                <span :class="{'dotted': oneDotted, 'dotted-none': !oneDotted, 'men-dotted': isMenCategory && oneDotted, 'women-dotted': isWomenCategory && oneDotted, 'men-dotted-none': isMenCategory && oneDotted, 'women-dotted-none': isWomenCategory && oneDotted}"></span>

                                <span :class="{'dotted': twoDotted, 'dotted-none': !twoDotted, 'men-dotted': isMenCategory && twoDotted, 'women-dotted': isWomenCategory && twoDotted, 'men-dotted-none': isMenCategory && oneDotted, 'women-dotted-none': isWomenCategory && oneDotted}"></span>

                                <span :class="{'dotted': threeDotted, 'dotted-none': !threeDotted, 'men-dotted': isMenCategory && threeDotted, 'women-dotted': isWomenCategory && threeDotted, 'men-dotted-none': isMenCategory && oneDotted, 'women-dotted-none': isWomenCategory && oneDotted}"></span>

                                <span :class="{'dotted': fourDotted, 'dotted-none': !fourDotted, 'men-dotted': isMenCategory && fourDotted, 'women-dotted': isWomenCategory && fourDotted, 'men-dotted-none': isMenCategory && oneDotted, 'women-dotted-none': isWomenCategory && oneDotted}"></span>

                                <span :class="{'dotted': fiveDotted, 'dotted-none': !fiveDotted, 'men-dotted': isMenCategory && fiveDotted, 'women-dotted': isWomenCategory && fiveDotted, 'men-dotted-none': isMenCategory && oneDotted, 'women-dotted-none': isWomenCategory && oneDotted}"></span>
                            </div>
                        </div>
                    </div>
                    <span class="line"></span>
                    <p class="text-netral">{{ dataProduct.description }}</p>
                    <span class="line"></span>
                    <p :class="{'price-men': isMenCategory, 'price-women': isWomenCategory}">${{ dataProduct.price }}</p>
                    <div class="button">
                        <button :class="{'buy-now-men': isMenCategory, 'buy-now-women': isWomenCategory}" @click="prevProduct">Previous Product</button>
                        <button :class="{'next-product-men': isMenCategory, 'next-product-women': isWomenCategory}" @click="nextProduct">Next Product</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div v-else>
        <!-- loader -->
        <div class="loader" v-if="isLoading">
            <div class="spin"></div>
        </div>
        <!-- unavailable page -->
        <div class="container">
            <span class="bg-unavailable"></span>
            <div class="box-unavailable">
                <div class="svg">
                    <svg width="1028" height="439" viewBox="0 0 1028 439" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M221.295 114.085C221.295 99.5795 226.49 87.1321 236.879 76.7429C247.268 66.3537 259.716 61.1591 274.222 61.1591C288.727 61.1591 301.175 66.3537 311.564 76.7429C321.953 87.1321 327.148 99.5795 327.148 114.085C327.148 128.591 321.953 141.038 311.564 151.428C301.175 161.817 288.727 167.011 274.222 167.011C264.616 167.011 255.795 164.561 247.759 159.661C239.722 154.956 233.253 148.585 228.352 140.548C223.648 132.707 221.295 123.886 221.295 114.085ZM556.494 114.085C556.494 99.5795 561.689 87.1321 572.078 76.7429C582.467 66.3537 594.915 61.1591 609.42 61.1591C623.926 61.1591 636.374 66.3537 646.763 76.7429C657.152 87.1321 662.347 99.5795 662.347 114.085C662.347 128.591 657.152 141.038 646.763 151.428C636.374 161.817 623.926 167.011 609.42 167.011C599.815 167.011 590.994 164.561 582.957 159.661C574.92 154.956 568.452 148.585 563.551 140.548C558.847 132.707 556.494 123.886 556.494 114.085Z" fill="black" fill-opacity="0.1"/>
                        <path d="M454.045 227.21C528.142 227.21 596.26 236.815 658.399 256.026C720.734 275.432 778.071 303.071 830.409 338.943V400.102C811.003 385.989 787.088 372.757 758.665 360.408C730.438 348.254 699.368 337.571 665.456 328.358C631.74 319.145 596.848 311.892 560.78 306.599C524.712 301.503 489.134 298.955 454.045 298.955C407.392 298.955 360.053 303.463 312.027 312.48C264.001 321.497 219.406 333.651 178.241 348.94C137.077 364.23 103.557 381.284 77.6818 400.102V338.943C130.02 303.071 187.259 275.432 249.398 256.026C311.733 236.815 379.949 227.21 454.045 227.21Z" fill="black" fill-opacity="0.1"/>
                        <path d="M133 38.5C235.4 53.7 299.333 28.5 318.5 14" stroke="black" stroke-opacity="0.1" stroke-width="25"/>
                        <path d="M739 38.3236C636.324 53.4142 572.218 28.3956 553 14" stroke="black" stroke-opacity="0.1" stroke-width="25"/>
                    </svg>
                </div>
                <p>This product is unavailable to show</p>
                <button class="next-product-unavailable" @click="nextProduct">Next Product</button>
                <button class="next-product-unavailable" @click="prevProduct">Previous Product</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "ProductDisplay",
    data() {
        return {
            apiUrl: "https://fakestoreapi.com/products/",
            currentIndex: 1,
            maxIndex: 20,
            dataProduct: null,
            dataCategory: null,
            dataRating: null,
            isLoading: false,
        }
    },
    created() {
        this.fetchData()
    },
    methods: {
        fetchData() {
            this.isLoading = true;
            fetch(this.apiUrl + this.currentIndex)
            .then(response => response.json())
            .then(data => {
                this.dataCategory = data.category
                this.dataRating = data.rating.rate

                if(this.isMenCategory || this.isWomenCategory) {
                    this.dataProduct = data
                }
            })
            .catch(error => {
                console.error('Error fetching data:', error)
            })
            .finally(() => {
                this.isLoading = false
            })
        },
        // fungsi untuk button next product
        nextProduct() {
            if (this.currentIndex < this.maxIndex) {
                this.currentIndex++
            } else {
                this.currentIndex = 1
            }

            this.fetchData()
        },
        // fungsi untuk button prev product
        prevProduct() {
            if (this.currentIndex !== 1) {
                this.currentIndex--
            } else {
                this.currentIndex = 1
            }

            this.fetchData()
        },
    },
    computed: {
        // pengkondisian untuk page section berdasarkan kategori
        isMenCategory() {
            return this.dataCategory === "men's clothing"
        },
        isWomenCategory() {
            return this.dataCategory === "women's clothing"
        },

        // pengkondisian untuk rating
        oneDotted() {
            return this.dataRating > "1"
        },
        twoDotted() {
            return this.dataRating > "2"
        },
        threeDotted() {
            return this.dataRating > "3"
        },
        fourDotted() {
            return this.dataRating > "4"
        },
        fiveDotted() {
            return this.dataRating > "5"
        }
    },
}
</script>

<style src="@/assets/style/global.css"></style>