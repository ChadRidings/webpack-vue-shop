<template>
    <div class="row heading">
        <div class="large-8 columns">
            <img src="assets/images/logo.png" class="logo" />
            <div class="menu">
                <span><a href="">Home</a></span>
                <span><a href="">About Us</a></span>
                <span><a href="">Occasions</a></span>
                <span><a href="">Order</a></span>
            </div>
        </div>
        <drop @drop="handleDrop">
            <div class="large-4 columns text-right">
                <div class="total">
                    Total Amount: ${{ totalAmount }} |
                </div>
                <div class="cart" style="background-image: url('./assets/images/cart.png')">
                    <div class="quantity">{{ totalQuantity }}</div>
                </div>
            </div>
        </drop>
    </div>
</template>

<style lang="scss">
    .heading {
        background-color: #28425a;
        color: #fff;
        font-weight: 500;
        line-height: 40px;
        margin: 0 auto;
        padding: 8px 0;
        text-transform: uppercase;

        .logo { display: inline-block; height: 40px; margin: 0 20px; }

        .menu {
            display: inline-block;

            a {
                color: #fff;

                &:hover {
                    color: #6ACDA9;
                }
            }

            span {
                margin: 0 10px;
            }
        }

        .total { display: inline-block; }

        .cart {
            background-repeat: no-repeat;
            background-size: cover;
            color: #000;
            display: block;
            float: right;
            height: 30px;
            line-height: 40px;
            position: relative;
            width: 32px;
            margin: 5px 20px 0 10px;

            .quantity {
                position: absolute;
                height: 30px;
                width: 32px;
                font-weight: bold;
                font-size: .9rem;
                text-align: center;
                line-height: 26px;
                padding-left: 6px;
            }
        }
    }
</style>

<script>
    var purchaseQuantity = [];
    var purchaseAmount = [];

    function keepDecimal(num) {
        return Number.parseFloat(num).toFixed(2);
    }

    export default {
        name: "heading",
        data: () => ({
            section: 'heading section',
            totalAmount: '',
            totalQuantity: ''

        }),
        methods: {
            handleDrop(data, event) {
                var price = parseInt(data.product.price);
                var quantity = parseInt(data.product.quantity);
                var amount = price * quantity;

                purchaseAmount.push(amount);
                purchaseQuantity.push(quantity);

                var grandTotal = purchaseAmount.reduce((accumulator, currentValue) => accumulator + currentValue);
                var grandQuantity = purchaseQuantity.reduce((accumulator, currentValue) => accumulator + currentValue);

                this.$data.totalAmount = keepDecimal(grandTotal);
                this.$data.totalQuantity = grandQuantity;
            },
        },
    }
</script>
