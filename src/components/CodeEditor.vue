<template>
    <div>
        <!-- <div class="toolbar">
            <button @click="boldText" class="toolbar-b" title="Bold">Bold</button>
            <button @click="italicText" class="toolbar-i" title="Italic">Italic</button>
            <br />
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
            <span>Color</span>
            <input
                @change="fontColorChange($event)"
                class="toolbar-color"
                type="color"
                value="#ff0000"
            />
            <span>Background</span>
            <input
                @change="backgroundColorChange($event)"
                class="toolbar-bg"
                type="color"
                value="#ffff00"
            />
            <br />
        </div>

        <div class="editor" contenteditable="true">
            <p>Write something</p>
        </div> -->
    </div>
</template>

<script>
export default {
    data() {
        return {}
    },
    /* methods: {
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
    }, */
}
</script>

<style>
</style>