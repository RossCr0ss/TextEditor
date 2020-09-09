<template>
    <div class="hello">
        <div
            class="relative-position cursor_normal none_outline"
            style="color: rgb(255, 255, 255); opacity: 1; border-radius: 6px; transform: rotate(0deg); border: 0px solid rgb(70, 144, 247); padding: 10px; text-align: center; letter-spacing: 0px; font-size: 32px; font-family: Aleo; font-weight: 300; text-decoration: none; box-shadow: rgb(0, 0, 0) 0px 0px 0px 0px; text-transform: initial; font-style: normal; z-index: 2002; text-shadow: rgba(0, 0, 0, 0.2) 2px 2px 0px; line-height: 1.5em;"
            spellcheck="false"
            :style="{ fontSize: fontSize + 'px', color: color, backgroundColor: backgroundColor }"
            contenteditable="true"
            @input.prevent="update"
        >
            <span
                style="background-color: rgb(248, 187, 208); padding-left:3px; padding-right: 3px; border-radius: 4px;"
            >Hi</span>
            <br />
            <span
                style="background-color: rgb(248, 187, 208); padding-left:3px; padding-right: 3px; border-radius: 4px;"
            >My lovely</span>
            <span style="color: rgb(136, 14, 79); font-size: 54px">little</span>
            <span style="color: rgb(186, 104, 200); background-color: rgb(248, 187, 0);">Ponny</span>
        </div>

        <div class="button-group">
            <button v-on:click="fontSize++">Increase font size</button>
            <button v-on:click="fontSize--">Decrease font size</button>

            <select v-model="color">
                <option disabled value>Select one of colors</option>
                <option>Blue</option>
                <option>Green</option>
                <option>Red</option>
            </select>
            <span>Selected color: {{ color }}</span>

            <select v-model="backgroundColor">
                <option disabled value>Select one of background color</option>
                <option>White</option>
                <option>Yellow</option>
                <option>Gray</option>
            </select>
            <span>Selected background color: {{ backgroundColor }}</span>
        </div>

        <!-- <div
            contenteditable="true"
            class="relative-position cursor_normal none_outline"
            style="color: rgb(255, 255, 255); opacity: 1; border-radius: 6px; transform: rotate(0deg); border: 0px solid rgb(70, 144, 247); padding: 10px; text-align: center; letter-spacing: 0px; font-size: 32px; font-family: Aleo; font-weight: 300; text-decoration: none; box-shadow: rgb(0, 0, 0) 0px 0px 0px 0px; text-transform: initial; font-style: normal; z-index: 2002; text-shadow: rgba(0, 0, 0, 0.2) 2px 2px 0px; line-height: 1.5em;"
            spellcheck="false"
        >
            <span
                style="background-color: rgb(248, 187, 208); padding-left:3px; padding-right: 3px; border-radius: 4px;"
            >
                <span>Hi</span>
            </span>
            <br />
            <span
                style="background-color: rgb(248, 187, 208); padding-left:3px; padding-right: 3px; border-radius: 4px;"
            >
                <span>My lovely</span>
                <span class style="color: rgb(136, 14, 79); font-size: 54px">little</span>
                <span
                    class
                    style="color: rgb(186, 104, 200); background-color: rgb(248, 187, 0);"
                >Ponny</span>
            </span>
        </div>

        <pre>
            {
            {
                text: "Hi",
                color: "rgb(248, 187, 208)",
                fontSize: "32px",
                background: "rgb(248, 187, 208)"
            },
            {
                text: "My lovely",
                color: "rgb(248, 187, 208)",
                fontSize: "32px",
                background: "rgb(248, 187, 208)"
            },
            {
                text: "little",
                color: "rgb(136, 14, 79)",
                fontSize: "54px",
                background: "rgb(248, 187, 208)"
            },
            {
                text: "Ponny",
                color: "rgb(186, 104, 200)",
                fontSize: "32px",
                background: "rgb(248, 187, 0)"
            },
            }
        </pre>-->
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    data() {
        return {
            fontSize: 32,
            color: 'black',
            backgroundColor: 'white',
            selected: ''
        }
    },
    methods: {
        update(event) {
            /* console.log('update', event.target.innerText) */
            let data = JSON.stringify({
                text: event.target.innerText,
                style: event.target.style
            })
            this.$emit('update', data)
        },
    },
}
</script>

<style scoped lang="scss">
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
