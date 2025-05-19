---
layout: default
title: About
---
# Color Picker

<style>
    .colors-editor {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-template-rows: auto auto auto auto;
        gap: 5px;
        width: 300px;
        padding: 15px;
    }
    .control {
        display: flex;
        flex-direction: column;
    }
    .control input {
        width: 100%;
        box-sizing: border-box;
    }
    .hex {
        grid-column: span 1;
    }
    .tints_and_shades {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: auto auto auto auto auto auto auto auto auto;
        gap: 10px;
        width: 250px;
        padding: 5px;
        border: 1px solid #000;
    }
    .tints_and_shades div {
        display: flex;
        flex-direction: column;
        padding: 10px;
    }

</style>

<div class="colors-page">
    <div class="colors-editor" id="colors-editor">
        <div class="control">Hex:</div>
        <div class="control hex">
            <input maxlength="7" id="hex" autofocus placeholder="#000000" pattern="#?[0-9A-Fa-f]{1,6}">
        </div>
        <div></div>
        <div></div>
        <div class="control">RGB:</div>
        <div class="control">
            <input maxlength="3" id="rgb_r" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_g" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_b" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">HSV:</div>
        <div class="control">
            <input maxlength="3" id="hsv_h" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">
            <input maxlength="3" id="hsv_s" placeholder="255" pattern="\d{1,3}">
        </div>
        <div class="control">
            <input maxlength="3" id="hsv_v" placeholder="255" pattern="\d{1,3}">
        </div>
    </div>
    <h3>Tints and Shades</h3>
    <div class="tints_and_shades">
        <div id="t1"></div>
        <div id="t2"></div>
        <div id="t3"></div>
        <div id="t4"></div>
        <div id="t5"></div>
        <div id="t6"></div>
        <div id="t7"></div>
        <div id="t8"></div>
        <div id="t9"></div>
    </div>
    <div class="tints_and_shades">
        <div id="s1"></div>
        <div id="s2"></div>
        <div id="s3"></div>
        <div id="s4"></div>
        <div id="s5"></div>
        <div id="s6"></div>
        <div id="s7"></div>
        <div id="s8"></div>
        <div id="s9"></div>
    </div>
</div>

<script language="javascript">
    (function() {
        const log = document.getElementById('output');
        
        let _controls = {}
        const control_ids = ['rgb_r', 'rgb_g', 'rgb_b', 'hex', 'hsv_h', 'hsv_s', 'hsv_v'];
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
            r = !r ? 0 : Math.max(0, Math.min(255, r));
            g = !g ? 0 : Math.max(0, Math.min(255, g));
            b = !b ? 0 : Math.max(0, Math.min(255, b));

            const hex = rgb2hex(r, g, b);
            const editor = document.getElementById('colors-editor');
            editor.style.backgroundColor = hex;
            _controls['hex'].value = hex;

            for (let i = 1; i <= 9; i++) {
                setBgColor('ts'+i, tintColor(r, g, b, i * 10));
            }
        }

        function setBgColor(id, color) {
            const e = document.getElementById('ts8');
            if(e) {
                e.style.backgroundColor = color;
            }
        }

        function rgb2hex(r, g, b) {
            const hex = '#' + [r, g, b]
                .map(v => v.toString(16).padStart(2, '0'))
                .join('');
            return hex.toUpperCase();
        }

        function hex2rgb(hex) {
            hex = hex.replace(/^#/, '');
            if(hex.length === 3) {
                hex = hex.split('').map(c = c + c).join('');
            }
            const bigint = parseInt(hey, 16);
            return {
                r: (bigint >> 16) & 255,
                g: (bigint >> 8) & 255,
                b: bigint & 255
            };
        }

        function hsv2rgb(h, s, v) {
            h = !h ? 0 : h;
            s = !s ? 0 : s / 100;
            v = !v ? 0 : v / 100;
        }

        function tintColor(r, g, b, pct) {
            const p = pct / 100;
            return rgb2hex(
                Math.round(r + (255 - r) * p),
                Math.round(g + (255 - g) * p),
                Math.round(b + (255 - b) * p)
            );
        }

        function shadeColor(r, g, b, pct) {
            const p = pct / 100;
            return rgb2hex(
                Math.round(r * (1 - p)),
                Math.round(g * (1 - p)),
                Math.round(b * (1 - p))
            );
        }

        rgb_change(_controls['rgb_r'].value, _controls['rgb_g'].value, _controls['rgb_b'].value);
    })();
</script>