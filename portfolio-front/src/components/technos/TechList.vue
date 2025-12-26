<template>
    <section id="technos">
        <h2>Technologies</h2>

        <div class="grid">
            <TechCard 
                v-for="tech in technos"
                :key="tech"
                :tech="technos[tech]"
            />
        </div>
    </section>
</template>

<script setup>
import TechCard from './TechCard.vue'
import { technos } from '@/data/technos'


</script>
