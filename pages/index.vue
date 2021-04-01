<template>
  <div class="container index">
    <section>
      <article>
        <h1>Hello there.</h1>
        <h2>
          I'm Paul Wallin, Web Developer, Teacher and some.
        </h2>
      </article>
      <figure>
        <img src="~assets/images/paul.svg" alt="Paul Wallin">
      </figure>
    </section>
  </div>
</template>
<style scoped>
.container.index section {
  display: grid;
  grid-template-columns: 70% 30%;
  gap: 1rem;
}
@media (max-width: 800px) {
  h1 {
    font-size: 3rem;
    line-height: 1.2;
  }
  .container.index section {
    grid-template-columns: 1fr 1fr;
  }
}
@media (max-width: 480px) {
  h1 {
    font-size: 3rem;
    line-height: 1.2;
  }
  .container.index section {
    grid-template-columns: 1fr;
  }
}
figure {
  display: flex;
  justify-content: center;
  align-content: center;
}
img {
  max-width: 100%;
  animation: fadein 2s;
}
@keyframes fadein {
    from { opacity: 0; }
    to   { opacity: 1; }
}
</style>
