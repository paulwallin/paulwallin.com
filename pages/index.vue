<template>
  <div class="container index">
    <section>
      <article>
        <h1>Hello there.</h1>
        <h2>
          I'm Paul Wallin, Web Developer, Teacher and wanna-be-musician.
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
