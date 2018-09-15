<template>
    <div class="row">
        <div class="large-12 header">
            This is the header
        </div>
    </div>
</template>

<style lang="scss">
    .header {
        background-color: #28425a;
        color: #fff;
        margin: 0 auto;
        padding: 8px 0;
    }
</style>

<script>
    export default {
        name: "header",
        data: () => ({
            section: 'header',
        }),
    }
</script>
