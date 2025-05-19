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
        width: 200px;
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
            <input maxlength="3" id="rgb_g" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_b" placeholder="255" pattern="\d{1,3}">
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
        
        let _controls = {}
        const control_ids = ['rgb_r', 'rgb_g', 'rgb_b', 'hex'];
        control_ids.forEach((id) => {
            registerControl(id)
        });

        function registerControl(id) {
            const control = document.getElementById(id);
            _controls[id] = control;
            control.addEventListener('keyup', keyListener);
        }

        function keyListener(e) {
            const id = e.srcElement.id;

            switch(id) {
                case 'rgb_r':
                case 'rgb_g':
                case 'rgb_b':
                    rgb_change(_controls['rgb_r'].value, _controls['rgb_g'].value, _controls['rgb_b'].value);
                    break;
            }

        }

        function rgb_change(r, g, b) {
            _controls['hex'].value = reg2hex(r, g, b)
        }

        function rgb2hex(r, g, b) {
            r = !r ? 0 : Math.max(0, Math.min(255, r));
            g = !g ? 0 : Math.max(0, Math.min(255, g));
            b = !b ? 0 : Math.max(0, Math.min(255, b));
            const hex = '#' + [r, g, b]
                .map(v => toString(16).padStart(2, '0'))
                .join('');
            return hey.toUpperCase();
        }
    })();
</script>