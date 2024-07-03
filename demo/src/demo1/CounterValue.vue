<template >
    <div>
        <span>Current value: {{ value }}</span>
    </div>
</template>
<script setup>
    defineProps({
        value: {
            type: Number,
            required: true,
        }
    });
</script>
<style lang="scss" scoped>
    
</style>