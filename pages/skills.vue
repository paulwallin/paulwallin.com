<template>
  <div class="container skills">
    <section>
      <article class="header" role="header">
        <h1>Skills</h1>
      </article>
      <article class="content">
        <div>
          <h1>Frontend</h1>
          <div class="skill-list">
            <div v-for="skill in frontendSkills" :key="skill.title">
              <h3>
                {{ skill.title }}
              </h3>
              <p>
                {{ skill.content }}
              </p>
            </div>
          </div>
        </div>
      </article>
      <article class="content">
        <h1>Links</h1>
        <ul>
          <li><a href="https://github.com/paulwallin?tab=repositories" title="GitHub">Github</a><br>(I use Github for teaching (classroom). I published a few projects I’m currently working on (this portfolio and a React-site)</li>
          <li><a href="https://codepen.io/paulwallin/collections/public" title="codepen">Codepen</a><br>I use codepen for fun, testing and examples for school</li>
          <li><a href="https://vigorous-jepsen-12eb09.netlify.app/" title="Arcada Nova">Arcada Nova</a><br>(Prototype, Nuxt &amp; vuetify, Netlify CMS in progress)
</li>
          <li><a href="https://www.arcadahallen.fi/" title="Arcadahallen">Arcadahallen</a><br> uppgrade with webshop ready to publish</li>
          <li><a href="https://www.theexpected.net/" title="the Expected">The Expected </a><br> Our band, New site with React-frontend in progress (see github)</li>
          <li><a href="https://wallin.fi/playground/portfolio/" title="Old portfolio">10+ yeas old portfolio</a><br>that I found in my archives... ;).
</li>
        </ul>
      </article>
    </section>
  </div>
</template>
<script>
export default {
  data: () => ({
    skills: [
      {
        title: 'HTML',
        content: 'Sturucte and semantics',
        type: 1
      },
      {
        title: 'CSS',
        content:
          'From layout to selectors from the farest corners. I do SCSS and testing out BEM for better structure',
        type: 1
      },
      {
        title: 'JS',
        content:
          'In the last couple of years I\'ve been working a lot on my JS-skills. God bases in Vanilla (>ES6) and my prefered library, Vue. But due to jobmarket I\'ve pick up React more seariously',
        type: 1
      },
      {
        title: 'PHP',
        content:
          'I used to work a lot with PHP, and I still also teach basic PHP-MySQL for my students',
        type: 2
      },
      {
        title: 'SQL',
        content:
          'My SQL is quite strong and I\'m comfortable with Relational DB\'s.',
        type: 2
      },
      {
        title: 'Teaching',
        content:
          'I\'ve been teaching programming for 10 years. My main subject is web developement, in which I\'ve bundled HTML, CSS, JS with invorements from Gith (classroom), Gulp and webpack, NPM/Yarn, frontend libraries Bootstrap, Material design, JSON and APIs, VUe and React',
        type: 3
      },
      {
        title: 'Adobe',
        content:
          'I know my way round Adobe products. PS, Ai and Xd to name few.',
        type: 3
      }
    ]
  }),
  computed: {
    // Filters
    frontendSkills () {
      const skills = this.skills
      const frontendSkills = skills.filter((item) => {
        return (item.type === 1)
      })
      return frontendSkills
    }
  }
}
</script>
<style lang="scss" scoped>
$green-gradient: linear-gradient(
  90deg,
  rgba(57, 187, 108, 1) 0%,
  rgba(68, 190, 212, 1) 100%
);

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
  &::after {
    content: "";
    position: absolute;
    right: -60px;
    top: 50%;
    width: 0;
    height: 0;
    border-top: 60px solid transparent;
    border-bottom: 60px solid transparent;
    border-left: 60px solid rgba(68, 190, 212, 1);
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
.skill-list {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  div { width: 200px}
  h3 { font-size: 1rem; }
  p { font-size: .9rem; }
}
</style>
