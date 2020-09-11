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


        <div class="toolbar">
            <div class="button-group">
                <button @click="boldText" class="toolbar-b" title="Bold">Bold</button>
                <button @click="italicText" class="toolbar-i" title="Italic">Italic</button>
            </div>
            <br />
            <div class="style-box">
                <select @change="fontStyleChange($event)" class="toolbar-font">
                    <option selected="selected" disabled="disabled">Font</option>
                    <option value="arial">Arial</option>
                    <option value="Courier New">Courier New</option>
                    <option value="georgia">Georgia</option>
                    <option value="impact">Impact</option>
                    <option value="roboto">Tahoma</option>
                    <option value="Times New Roman">Times New Roman</option>
                    <option value="verdana">Verdana</option>
                </select>
                <select @change="fontSizeChange($event)" class="toolbar-size">
                    <option selected="selected" disabled="disabled">Size</option>
                    <option value="1">10px</option>
                    <option value="2">12px</option>
                    <option value="3">14px</option>
                    <option value="4">16px</option>
                    <option value="5">18px</option>
                    <option value="6">21px</option>
                    <option value="7">26px</option>
                </select>

                <div class="box-color">
                    <label for="color">Color</label>
                    <input
                        @change="fontColorChange($event)"
                        class="toolbar-color"
                        type="color"
                        id="color"
                        value="#ff0000"
                    />
                </div>

                <div class="box-background">
                    <label for="background">Background</label>
                    <input
                        @change="backgroundColorChange($event)"
                        class="toolbar-bg"
                        type="color"
                        id="background"
                        value="#ffff00"
                    />
                </div>
            </div>
            <br />
        </div>
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
            selected: '',
        }
    },
    methods: {
        update(event) {
            let dataArr = event.target.children
            console.log((dataArr));
            let data = [];
            for (let i = 0; i < dataArr.length; i++) {
                
                /* if (dataArr[i].childNodes.length > 1 ) {
                    console.log('good');
                } */
                
                let item = {
                    backgroundColor: dataArr[i].style.backgroundColor,
                    color: dataArr[i].style.color,
                    fontSize: dataArr[i].style.fontSize,
                    textContent: dataArr[i].textContent
                }
                data.push(item)
                
            }

            console.log(JSON.stringify(data));

            this.$emit('update', data)
        },

        boldText() {
            document.execCommand('bold', false, null)
            return false
        },
        italicText() {
            document.execCommand('italic', false, null)
            return false
        },
        fontStyleChange(event) {
            document.execCommand('styleWithCSS', false, true)
            document.execCommand('fontName', false, event.target.value)
            document.execCommand('styleWithCSS', false, false)
        },
        fontSizeChange(event) {
            document.execCommand('styleWithCSS', false, true)
            document.execCommand('fontSize', false, event.target.value)
            document.execCommand('styleWithCSS', false, false)
        },
        fontColorChange(event) {
            document.execCommand('styleWithCSS', false, true)
            document.execCommand('foreColor', false, event.target.value)
            document.execCommand('styleWithCSS', false, false)
        },
        backgroundColorChange(event) {
            document.execCommand('styleWithCSS', false, true)
            document.execCommand('hiliteColor', false, event.target.value)
            document.execCommand('styleWithCSS', false, false)
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

.toolbar {
    display: flex;
    flex-direction: column;
    align-items: center;

    .button-group {
        margin: 1rem 0;

        button {
            margin: 0 1rem;
        }
    }

    .style-box {
        display: flex;
        justify-content: space-around;
        align-items: center;
        min-width: 600px;

        div > label {
            margin-right: 0.5rem;
        }
    }
}
</style>
