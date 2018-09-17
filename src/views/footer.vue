<template>
    <div class="row footing">
        <div class="large-4 columns">
            <h4>Get to know us</h4>
            <ul>
                <li><a href="">About Us</a></li>
                <li><a href="">Careers</a></li>
                <li><a href="">Media</a></li>
                <li><a href="">Security &amp; Privacy</a></li>
            </ul>
        </div>

        <div class="large-4 columns">
            <h4>Learn more about</h4>
            <ul>
                <li><a href="">Blog</a></li>
                <li><a href="">Find a Florist</a></li>
                <li><a href="">Floral Tips &amp; Inspiration</a></li>
                <li><a href="">Sitemap</a></li>
            </ul>
        </div>

        <div class="large-4 columns">
            <h4>Shop vicky's</h4>
            <ul>
                <li><a href="">Same-Day Flower Delivery</a></li>
                <li><a href="">Birthday Flowers</a></li>
                <li><a href="">Funeral &amp; Sympathy Flowers</a></li>
                <li><a href="">International Flower Delivery</a></li>
            </ul>
        </div>
    </div>
</template>

<style lang="scss">
    .footing {
        background-color: #24435a;
        color: #fff;
        margin: 0 auto;
        padding: 50px 0;
        text-align: center;

        a {
            color: #fff;

            &:hover {
                color: #6ACDA9;
            }
        }

        h4 { color: #d33169; font-size: .95rem; font-weight: bold; text-transform: uppercase; }

        ul {
            font-size: .9rem;
            font-weight: 500;
            list-style-type: none;

            li { padding: 5px 0; }
        }
    }
</style>

<script>
    export default {
        name: "footing",
        data: () => ({
            section: 'footing section',
        }),
    }
</script>
