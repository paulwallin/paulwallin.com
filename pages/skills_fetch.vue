<template>
  <div class="container skills">
    <article>
      <h1>Skills</h1>
      <section>
        <article>
          <h1>Fluent</h1>
          <h3>Stuff i can do</h3>
          <ul v-for="skill in skills" :key="skill.id">
            <li v-for="fluent in skill.fluents" :key="fluent.id">
              {{ fluent.title }}
            </li>
          </ul>
        </article>
        <article>
          <h1>Solid</h1>
          <h3>pretty good knowledge</h3>
          <ul>
            <li>Wordpress</li>
            <li>PHP</li>
            <li>MySQL</li>
            <li>Node</li>
            <li>express</li>
            <li>Jamstack</li>
          </ul>
          <p>and the list goes on...</p>
        </article>
        <article>
          <h1>Interests</h1>
        </article>
        <article>
          <h1>Deprecated</h1>
        </article>
      </section>
    </article>
  </div>
</template>
<script>
// import axios from 'axios';

export default {
  data () {
    return {
      skills: []
    }
  },
  async fetch () {
    this.skills = await fetch('http://localhost:80/skills').then(res =>
      res.json()
    )
  }
}
</script>
