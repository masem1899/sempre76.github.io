---
layout: default
title: About
---
# Color Picker

<style>
    .colors-editor {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-template-rows: auto auto;
        gap: 10px;
        width: 300px;
    }
    .control {
        display: flex;
        flex-direction: column;
    }
    .hex {
        grid-column: span 2;
    }
</style>

<div class="colors-page">
    <div class="colors-editor">
        <div class="control">
            <input maxlength="3" id="rgb_r" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_g" placeholder="255" pattern="\d{1,3}>
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_b" placeholder="255" pattern="\d{1,3}>
        </div>
        <div class="control hex">
            <input maxlength="7" id="hex" placeholder="#000000" pattern="#?[0-9A-Fa-f]{1,6}">
        </div>
    </div>
</div>
<div id="output">
</div>

<script language="javascript">
    (function() {
        const log = document.getElementById('output');
        
        const control_ids = ['rgb_r', 'rgb_g', 'rgb_b'];
        control_ids.forEach((id) => {
            registerControl(id)
        });

        function registerControl(id) {
            const control = document.getElementById(id);
            control.addEventListener('keyup', keyListener);
        }

        function keyListener(e) {
            switch(e.srcElement.id) {
                case 'rgb_r':
                case 'rgb_g':
                case 'rgb_b':
                    console.log('event listener');
            }

        }
    })();
</script>