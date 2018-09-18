<template>
    <div class="main-content">
        <Header />
        <Products />
        <Footer />
    </div>
</template>

<style lang="scss">
    .row { max-width: 1170px; }
    
    .main-content {
        margin: 0 auto;
        max-width: 1170px;
        padding: 0;
    }
</style>

<script>
    import Header from './header';
    import Products from './products';
    import Footer from './footer';

    export default {
        name: "main-content",
        components: {
            Header,
            Products,
            Footer
        },
        data: () => ({
            section: 'Main',
        })
    }
</script>
