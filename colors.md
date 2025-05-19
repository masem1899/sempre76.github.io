---
layout: default
title: About
---
# Color Picker

<div class="colors-page">
    <div class="colors-editor">
        <input maxlength="3" id="rgb_r" placeholder="R" type="number" onclick="rgb_changed();">
        <input maxlength="3" id="rgb_g" placeholder="G" type="number" onclick="rgb_changed();">
        <input maxlength="3" id="rgb_b" placeholder="B" type="number" onclick="rgb_changed();">
    </div>
</div>

<script language="javascript">
    function rgb_changed() {
        console.log('cange')
    }
</script>