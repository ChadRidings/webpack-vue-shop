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
                <img :src="product.image" /><br />
                <div class="title"><p>{{ product.name }}</p></div>
                <div class="price">{{ product.price }}</div>
                <div class="select-box">
                   {{ product.quantity }}
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    .products {
        background-color: #bdbdbd;
        color: #4a4a4a;
        margin: 0 auto;
        padding: 20px;

        .details {
            margin: 0 0 30px;
        }

        h1 {
            color: #d33169;
            font-size: 1.8rem;
            font-weight: bold;
        }

        p {
            font-weight: 500;
        }

        .title {
            text-align: center;
            width: 100%;
        }
    }
</style>

<script>
    export default {
        name: 'products',
        data: () => ({
            products: [
                {
                    "id": 1,
                    "name": "Sunflower Melody",
                    "price": 30.00,
                    "quantity": 12,
                    "image": "assets/images/flower-1.png"
                },
                {
                    "id": 2,
                    "name": "Spring Mix",
                    "price": 35.00,
                    "quantity": 9,
                    "image": "assets/images/flower-2.png"
                },
                {
                    "id": 3,
                    "name": "Colorful Arrangement",
                    "price": 40.00,
                    "quantity": 18,
                    "image": "assets/images/flower-3.png"
                },
                {
                    "id": 4,
                    "name": "Tulip Season",
                    "price": 50.00,
                    "quantity": 34,
                    "image": "assets/images/flower-4.png"
                }
            ]
        })
    }
</script>
