<template>
    <div class="wrapper">
        <pre>{{ jsonData | json }}</pre>
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

<style>
.wrapper {
    margin: 1rem auto;
}
</style>