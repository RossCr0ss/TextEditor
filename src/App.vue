<template>
    <div id="app">
        <TextBlock @update="onUpdate" />
        <InfoBlock :jsonData="jsonData" />

        
        <!-- <InfoBlock v-model="jsonData1" /> -->
    </div>
</template>

<script>
import TextBlock from '@/components/TextBlock.vue'
import InfoBlock from '@/components/InfoBlock.vue'
export default {
    name: 'App',
    data() {
        return {
            jsonData: null,
        }
    },
    components: {
        TextBlock,
        InfoBlock,
    },
    methods: {
        onUpdate(data) {
            /* console.log('child component text', data) */
            this.jsonData = data
            /* console.log(this.jsonData) */
        },
    },
}
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
