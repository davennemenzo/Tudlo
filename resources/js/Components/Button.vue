<script setup>
defineProps({
    background: {
        type: String,
        default: '#26A69A',
    },
    textColor: {
        type: String,
        default: '#FFFFFF',
    },
    hoverOpacity: {
        type: String,
        default: 'opacity',
    },

});
</script>

<template>
    <button :style="{ backgroundColor: background, color: textColor, }" :class="hoverOpacity">
        <slot></slot>
    </button>
</template>

<style scoped>
.opacity:hover {
    opacity: 0.8;
}
.gray {
    background-color: gray;
}
</style>
