<template>
  <div class="container about">
    <section>
      <article class="header">
        <h1>About</h1>
      </article>
      <article class="content">
        <h1>About me</h1>
        <h3>Who is this guy?</h3>
        <figure>
          <img src="~assets/images/paul.svg" alt="Paul Wallin">
        </figure>
      </article>
      <article class="content">
        <h1>Contact</h1>
        <h3>040 525 5245 / paul@wallin.fi</h3>
      </article>
    </section>
  </div>
</template>
<style lang="scss" scoped>
$green-gradient: linear-gradient(90deg, rgba(57,187,108,1) 0%, rgba(68,190,212,1) 100%);

section {
  display: grid;
  width: 100%;
  grid-template-columns: 20% 80%;
  grid-template-rows: 1fr 1fr;
  gap: 0;
  box-shadow: 0 0 35px 15px rgba(0, 0, 0, 0.2);
}
article.header {
  background-color: var(--pw-green);
  background: $green-gradient;
  display: flex;
  align-items: center;
  justify-content: center;
  grid-column: span 1;
  grid-row: span 2;
  h1 {
    color: var(--pw-white);
  }
  &::after{
    content: '';
    position: absolute;
    right: -60px;
    top: 50%;
    width: 0;
    height: 0;
    border-top: 60px solid transparent;
    border-bottom: 60px solid transparent;
    border-left: 60px solid rgba(68,190,212,1);
    transform: translateY(-60px);
    clear: both;
    z-index: 10;
}
}
article.content {
  grid-column: span 1;
  grid-row: span 1;
  background-color: var(--pw-white);
}
img { width: 100px;}
</style>
