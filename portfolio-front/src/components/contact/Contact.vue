<template>
    <section id="contact">
        <h2>Contact</h2>

        <form>
            <input type="text" placeholder="Nom" />
            <input type="email" placeholder="Email" />
            <textarea placeholder="Message"></textarea>
            <button>Envoyer</button>
        </form>
    </section>
</template>

<style scoped>
form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    max-width: 400px;
}
</style>
