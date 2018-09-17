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
        <div class="large-4 columns text-right">
            <div class="total">
                Total Amount: $35.00 |
            </div>
            <div class="cart" style="background-image: url('./assets/images/cart.png')">
                <div class="quantity">0</div>
            </div>
        </div>
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
    export default {
        name: "heading",
        data: () => ({
            section: 'heading section',
        }),
    }
</script>
