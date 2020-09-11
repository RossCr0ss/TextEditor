<template>
    <div class="wrapper">
        <p class="box">{{ jsonData | json }}</p>
    </div>
</template>

<script>
export default {
    props: ['jsonData'],
    filters: {
        json(value) {
            return JSON.stringify(value)
        },
    },
}
</script>

<style lang="scss">
.wrapper {
    margin: 1rem auto;

    .box{
        max-width: 600px;
        margin: 0 auto
    }
}
</style>