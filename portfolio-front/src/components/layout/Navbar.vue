<template>
    <nav class="navbar">
        <div class="logo">Mon Portfolio</div>

        <button class="burger" @click="open = !open">☰</button>

        <ul :class="{ open }">
            <li><a href="#home">Accueil</a></li>
            <li><a href="#projects">Projets</a></li>
            <li><a href="#technos">Technos</a></li>
            <li><a href="#experience">Expérience</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
</template>

<script setup>
import { ref } from 'vue'
const open = ref(false)
</script>

<style scoped>
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: var(--bg);
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 1000;
}
.logo {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--primary);
}
.burger {
    display: none;
    font-size: 1.5rem;
    background: none;
    border: none;
    cursor: pointer;
    color: var(--text);
}
ul {
    list-style: none;
    display: flex;
    gap: 1.5rem;
}
ul li a {
    text-decoration: none;
    color: var(--text);
    font-weight: 500;
}
ul.open {
    display: block;
    position: absolute;
    top: 60px;
    right: 20px;
    background: var(--bg);
    border: 1px solid var(--border);
    padding: 1rem;
    border-radius: 8px;
}

@media (max-width: 768px) {
    .burger {
        display: block;
    }
    ul {
        display: none;
        flex-direction: column;
        gap: 1rem;
    }
}
</style>
