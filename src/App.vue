<template>
    <div id="app">
        <TextBlock @update="onUpdate" />
        <InfoBlock :jsonData="jsonData" />

        <CodeEditor />

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
        CodeEditor,
    },
    methods: {
        onUpdate(data) {
            this.jsonData = data
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
