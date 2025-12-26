<template>
  <section id="home" class="hero">
    <img src="/profile.jpg" alt="Photo de moi" />
    <div>
      <h1>Salut, moi c’est Maxime</h1>
      <p>
        Étudiant en informatique, passionné par le développement web,
        les projets concrets et les systèmes bien pensés.
      </p>
    </div>
  </section>
</template>

<style scoped>
.hero {
  display: flex;
  gap: 2rem;
  align-items: center;
}
img {
  width: 180px;
  border-radius: 50%;
}
@media (max-width: 768px) {
  .hero { flex-direction: column; text-align: center; }
}
</style>
