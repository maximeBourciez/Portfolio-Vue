<template>
    <article class="project-card">
        <img class="cover" :src="project.cover" :alt="project.nom" />

        <div class="content">
            <header>
                <h3>{{ project.nom }}</h3>
                <span class="type" :class="project.type">
                    {{ typeLabel }}
                </span>
            </header>

            <p class="period">
                {{ formatDate(project.debut) }} –
                {{ project.fin ? formatDate(project.fin) : 'En cours' }}
            </p>

            <p class="description">{{ project.description }}</p>

            <div class="tech-list">
                <TechBadge v-for="techKey in project.technos" :key="techKey" :tech="technosMap[techKey]" />
            </div>
        </div>
    </article>
</template>

<script setup>
import { computed } from 'vue'
import TechBadge from '@/components/technos/TechBadge.vue'
import { technos as technosMap } from '@/data/technos'

const props = defineProps({
    project: { type: Object, required: true }
})

const typeLabel = computed(() => ({
    pro: 'Professionnel',
    perso: 'Personnel',
    univ: 'Universitaire'
}[props.project.type]))

const formatDate = (value) => {
    const [y, m] = value.split('-')
    return `${m}/${y}`
}
</script>

<style scoped>
.project-card {
    display: flex;
    flex-direction: column;
    background: var(--bg-light);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
    transition: transform 0.2s ease;
    color: var(--text);
    width: 100%;
    max-width: 700px;
    /* pour pas coller aux bords */
    margin: 1rem auto;
    border-color: var(--border);
    border: 1px solid var(--border);
}

.project-card:hover {
    transform: translateY(-4px);
}

.cover {
    width: 100%;
    height: 180px;
    object-fit: cover;
}

.content {
    padding: 1.2rem;
}

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.type {
    font-size: 0.7rem;
    padding: 0.2rem 0.5rem;
    border-radius: 4px;
}

.type.pro {
    background: var(--bg);
    color: var(--primary);
}

.type.perso {
    background: var(--bg);
    color: var(--success);
}

.type.univ {
    background: var(--bg);
    color: var(--warning);
}

.period {
    font-size: 0.8rem;
    color: var(--text-muted);
    margin-top: 0.25rem;
}

.description {
    margin-top: 0.5rem;
    font-size: 0.9rem;
}

.tech-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 0.75rem;
}
</style>
