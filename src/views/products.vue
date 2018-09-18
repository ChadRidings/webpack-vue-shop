<template>
    <div class="products">
        <div class="row details">
            <div class="large-12 column">
                <h1>Top Products</h1>
                <p>
                    To add desired products to the cart, simply drag a product image to
                    the cart icon found at the top right of the page.
                </p>
            </div>
        </div>

        <div class="row">
            <div
                class="large-3 columns"
                v-for="product in products"
                v-bind:key="product.id"
            >
                <drag :transfer-data="{ product }">
                    <img class="product-image" :src="product.image" /><br />
                </drag>
                <div class="title">{{ product.name }}</div>
                <div class="price">${{ product.price }}</div>
                <div class="select-box">
                    <select v-model="product.quantity" style="background-image: url(assets/images/arrow.png);">
                        <option v-for="n in 20" v-bind:key="n">{{ n }}</option>
                    </select>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    .products {
        background-color: #bdbdbd;
        color: #4a4a4a;
        font-weight: 500;
        margin: 0 auto;
        padding: 20px;

        h1 { color: #d33169; font-size: 1.8rem; font-weight: bold; }

        .details { margin: 0 0 30px; }
        .title { margin-top: 30px; text-align: center; }
        .price { color: #d33169; font-weight: bold; text-align: center; }
        
        .select-box {
            margin-top: 30px;

            select {
                background: #fff no-repeat 65px center;
                background-size: 25%;
                border: 1px solid #24435a;
                display: block;
                margin: 0 auto;
                max-width: 100px;
            }
        }
    }
</style>

<script>
    function keepDecimal(num) {
        return Number.parseFloat(num).toFixed(2);
    }

    export default {
        name: 'products',
        data: () => ({
            products: [{
                    "id": 1,
                    "name": "Sunflower Melody",
                    "price": keepDecimal(30.00),
                    "quantity": 1,
                    "image": "assets/images/flower-1.png"
                }, {
                    "id": 2,
                    "name": "Spring Mix",
                    "price": keepDecimal(35.00),
                    "quantity": 1,
                    "image": "assets/images/flower-2.png"
                }, {
                    "id": 3,
                    "name": "Colorful Arrangement",
                    "price": keepDecimal(40.00),
                    "quantity": 1,
                    "image": "assets/images/flower-3.png"
                }, {
                    "id": 4,
                    "name": "Tulip Season",
                    "price": keepDecimal(50.00),
                    "quantity": 1,
                    "image": "assets/images/flower-4.png"
                }
            ]
        })
    }
</script>
