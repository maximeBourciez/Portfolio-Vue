<template>
    <span class="tech-badge">
        <img :src="tech.logo" />
        {{ tech.label }}
    </span>
</template>

<script setup>
defineProps({
    tech: { type: Object, required: true }
})
</script>

<style scoped>
.tech-badge {
    display: inline-flex;
    align-items: center;
    gap: .4rem;
    padding: .25rem .6rem;
    background: var(--bg);
    border-radius: 999px;
    font-size: .75rem;
    border: 1px solid var(--border);
}

.tech-badge img {
    width: 14px;
    height: 14px;
}
</style>
