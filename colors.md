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
</style>

<div class="colors-page">
    <div class="colors-editor">
        <div class="control">
            <input maxlength="3" id="rgb_r" placeholder="R" type="number">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_g" placeholder="G" type="number">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_b" placeholder="B" type="number">
        </div>
    </div>
</div>
<div id="output">
</div>

<script language="javascript">
    (function() {
        const log = document.getElementById('output');
        const rgb_r = document.getElementById('rgb_r');
        rgb_r.addEventListener('keydown', logKey);

        function logKey(e) {
            log.textContent += ` ${e.code}`;
        }
    })();
</script>