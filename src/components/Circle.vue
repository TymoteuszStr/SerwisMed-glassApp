<template>
<div class="circle" :style="`width:${size}px; height:${size}px`"></div>
</template>

<script>
export default {
name: "Circle",
props:{
    size: {
        type: Number,
        required: true
    },
}

}
</script>

<style lang="scss" scoped>
.circle{
    background-color:white;
    background: linear-gradient(rgba(255,255,255,.8),rgba(255,255,255, .3));
    position: absolute;
    border-radius:50%;
    z-index: 2;
}
</style>