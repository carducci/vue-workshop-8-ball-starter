<template>
    <div class="cover-slot"><slot></slot></div>
</template>

<script>
    export default {
        name: "TheCoverSlot"
    }
</script>

<style scoped>
    .cover-slot {
        position: absolute;
        margin: -200px 0 0 -200px;
        border-radius: 50%;
        width: 50%;
        height: 50%;
        background: white;
        left: 75%;
        font-family: Helvetica;
        top: 75%;
        text-align: center;
        color: black;
        line-height: 1.35;
        font-size: 150px;
    }
</style>