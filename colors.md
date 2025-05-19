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
            <input maxlength="3" id="rgb_r" placeholder="R" type="number" onchange="rgb_changed();">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_g" placeholder="G" type="number" onchange="rgb_changed();">
        </div>
        <div class="control">
            <input maxlength="3" id="rgb_b" placeholder="B" type="number" onchange="rgb_changed();">
        </div>
    </div>
</div>

<script language="javascript">
    function rgb_changed() {
        console.log('cange')
    }
</script>