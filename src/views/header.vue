<template>
    <div class="row heading">
        <div class="heading-left">
            <img src="assets/images/logo.png" class="logo" />
            <div class="menu">
                <span><a href="">Home</a></span>
                <span><a href="">About Us</a></span>
                <span><a href="">Occasions</a></span>
                <span><a href="">Order</a></span>
            </div>
        </div>
        <drop @drop="handleDrop" class="heading-right">
            <div class="total">
                Total Amount: ${{ totalAmount }} |
            </div>
            <div class="cart" style="background-image: url('./assets/images/cart.png')">
                <div class="quantity">{{ totalQuantity }}</div>
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

        .heading-left {
            display: inline-block;
            width: calc(100% - 300px);

            @media screen and (max-width: 800px) {
                display: block;
                width: 100%;
            }
        }

        .heading-right {
            display: inline-block;
            padding: 0 10px;
            width: 290px;
            vertical-align: top;

            @media screen and (max-width: 800px) {
                display: block;
                width: 100%;
            }
        }

        .logo {
            display: inline-block;
            height: 40px;
            margin: 0 20px;

            @media screen and (max-width: 800px) {
                display: block;
                margin: 0 auto;
            }
        }

        .menu {
            display: inline-block;

            @media screen and (max-width: 800px) {
                display: block;
                text-align: center;
            }

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

        .total {
            display: inline-block;
            width: calc(100% - 37px);
            text-align: right;
        }

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
            margin: 5px 0 0 5px;

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
            totalAmount: '0',
            totalQuantity: '0'

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
