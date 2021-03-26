/* eslint-disable no-console */
<template>
  <div class="nav">
    <nuxt-link to="/" class="brand">
      <img src="~assets/images/paul.svg" alt="paulwallin.com">
    </nuxt-link>
    <nav>
      <nuxt-link to="/">
        Home
      </nuxt-link>
      <nuxt-link to="/skills">
        Skills
      </nuxt-link>
      <nuxt-link to="/about">
        About &amp; contact
      </nuxt-link>
    </nav>
  </div>
</template>
<script>
export default {
  data () {
    return {
      items: [
        { title: 'Startsidan', icon: 'mdi-home-city', link: '/' },
        { title: 'Kontakta oss', icon: 'mdi-contacts', link: '/contact' },
        { title: 'Fastighetsförvaltning', icon: 'mdi-account-group-outline', link: '/fastighetsforvaltning' }
      ],
      drawer: false,
      group: null
    }
  },
  methods: {
    menuItems () {
      return this.items
    }
  }
}
</script>
<style lang="scss" scoped>
//colors:
$pw-black: rgb(26, 26, 26);
$pw-white: #f2f2f2;
$pw-pink: #ED5A77;
$pw-light-pink: #D67EA5;
$pw-green: #39BB6C;
$pw-blue:#44BED4;
$pw-orange: #F09067;

$orange-gradient: linear-gradient(142deg, rgba(237,90,119,1) 0%, rgba(240,144,103,1) 100%);
$green-gradient: linear-gradient(142deg, rgba(57,187,108,1) 0%, rgba(68,190,212,1) 100%);

/* =NAVIGATION
*****************/
.nav {
  display: flex;
  width: calc(100% - 2rem);
  justify-content: space-between;
  align-items: center;
  height: 60px;
  height: 60px;
  padding: 0;
  background-color: transparent;
  align-items: flex-start;

  a {
    position: relative;
    z-index: 1;
    display: inline-block;
    padding: 5px 15px;
    text-decoration: none;
    background: $pw-orange;
    background: $orange-gradient;
  }
  a:before {
  content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: $pw-orange;
    opacity: 0;
    transition: opacity 0.4s;
    z-index: -1;
  }
a:hover:before {
  opacity: 1;
}
  a:after {
    content: " ";
    display: block;
    position: relative;
    top: 5px;
    width: 100%;
    height: 4px;
    background-color: $pw-orange;
  }
  a:hover {
    background-color: $pw-orange;
    background: $pw-orange;
  }
 .nuxt-link-exact-active {
    background: $green-gradient;
    color: $pw-black;
  }
 .nuxt-link-exact-active:after {
    background-color: $pw-orange;
  }
  .nuxt-link-exact-active:hover {
    background-color: $pw-orange;
  }
}
/*= Brand
    ****************/
.brand {
  font-family: "Pacifico", sans-serif;
  font-weight: 700;
  font-size: 1.5em;
  color: var(--pw-black);
  text-decoration: none;
  width: 50px;
  margin-left: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: $pw-orange;
  &.nuxt-link-exact-active {
    width: 50px;
    background-color: $pw-orange;
  }
  &.nuxt-link-exact-active:after, &.nuxt-link-active:after {
    content: " ";
    display: none;
  }
}
</style>
