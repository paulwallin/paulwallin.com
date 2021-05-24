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
        <div>
          <h1>Backend</h1>
          <div class="skill-list">
            <div v-for="skill in backendSkills" :key="skill.title">
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
        <div>
          <h1>Other...</h1>
          <div class="skill-list">
            <div v-for="skill in otherSkills" :key="skill.title">
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
        <h1>More to come...</h1>
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
        content: 'Sturucte and semantics, usability and accessibility makes a difference',
        type: 1
      },
      {
        title: 'CSS',
        content:
          'From CSS grid and flex layouts to selectors from the farest corners. I do SCSS and sometimes BEM for better structure',
        type: 1
      },
      {
        title: 'JS',
        content:
          'In the last couple of years I\'ve been working a lot on my JS-skills so I can teach the fundementals and move forward to all the hip libraries. Good bases in Vanilla (>ES6) and my prefered library, Vue. But due to the jobmarket demand I\'ve also picked up React',
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
          'I\'ve been teaching programming for 10 years. My main subject is web development, in which I\'ve bundled HTML, CSS, JS with environments from Gih (classroom), Gulp and webpack, NPM/Yarn, frontend libraries Bootstrap, Design systems, JSON and APIs, Vue and React',
        type: 3
      },
      {
        title: 'Adobe',
        content:
          'I know my way round Adobe products. PS, Ai and Xd to name a few.',
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
    },
    backendSkills () {
      const skills = this.skills
      const backendSkills = skills.filter((item) => {
        return (item.type === 2)
      })
      return backendSkills
    },
    otherSkills () {
      const skills = this.skills
      const otherSkills = skills.filter((item) => {
        return (item.type === 3)
      })
      return otherSkills
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
  grid-row: span 4;
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
  p { font-size: .9rem; text-align: justify; }
}
</style>
