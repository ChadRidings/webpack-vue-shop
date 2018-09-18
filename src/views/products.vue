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
                    <select v-model="product.quantity">
                        <option value="1">1</option>
                        <option value="2">2</option>
                        <option value="3">3</option>
                        <option value="4">4</option>
                        <option value="5">5</option>
                        <option value="6">6</option>
                        <option value="7">7</option>
                        <option value="8">8</option>
                        <option value="9">9</option>
                        <option value="10">10</option>
                        <option value="11">11</option>
                        <option value="12">12</option>
                        <option value="13">13</option>
                        <option value="14">14</option>
                        <option value="15">15</option>
                        <option value="16">16</option>
                        <option value="17">17</option>
                        <option value="18">18</option>
                        <option value="19">19</option>
                        <option value="20">20</option>
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
                display: block;
                margin: 0 auto;
                max-width: 100px;
            }
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
                    "quantity": 1,
                    "image": "assets/images/flower-1.png"
                },
                {
                    "id": 2,
                    "name": "Spring Mix",
                    "price": 35.00,
                    "quantity": 1,
                    "image": "assets/images/flower-2.png"
                },
                {
                    "id": 3,
                    "name": "Colorful Arrangement",
                    "price": 40.00,
                    "quantity": 1,
                    "image": "assets/images/flower-3.png"
                },
                {
                    "id": 4,
                    "name": "Tulip Season",
                    "price": 50.00,
                    "quantity": 1,
                    "image": "assets/images/flower-4.png"
                }
            ]
        })
    }
</script>
