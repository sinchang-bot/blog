<template>
  <header>
    <div class="header">
      <saber-link class="title" rel="author" to="/">{{ siteTitle }}</saber-link>
      <nav>
        <button @click="expanded = !expanded">
          <svg viewBox="0 0 18 15" width="18px" height="15px">
            <path
              d="M18,1.484c0,0.82-0.665,1.484-1.484,1.484H1.484C0.665,2.969,0,2.304,0,1.484l0,0C0,0.665,0.665,0,1.484,0 h15.032C17.335,0,18,0.665,18,1.484L18,1.484z M18,7.516C18,8.335,17.335,9,16.516,9H1.484C0.665,9,0,8.335,0,7.516l0,0 c0-0.82,0.665-1.484,1.484-1.484h15.032C17.335,6.031,18,6.696,18,7.516L18,7.516z M18,13.516C18,14.335,17.335,15,16.516,15H1.484 C0.665,15,0,14.335,0,13.516l0,0c0-0.82,0.665-1.483,1.484-1.483h15.032C17.335,12.031,18,12.695,18,13.516L18,13.516z"
            ></path>
          </svg>
        </button>
        <div :class="{expanded: expanded}" class="nav-links" v-if="$themeConfig.nav">
          <saber-link
            :key="index"
            class="nav-link"
            v-for="(navItem, index) in $themeConfig.nav"
            :to="navItem.link"
          >{{ navItem.text }}</saber-link>
        </div>
        <a class="feed-subscribe" v-if="feedLink" :href="feedLink">
          <svg class="svg-icon orange">
            <use :xlink:href="getSvg('rss')"></use>
          </svg>
        </a>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import '../styles/variables.scss';

header {
  background: #fff;
  padding: 0 10vw;
}

.header {
  height: 50px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  position: relative;
  max-width: 750px;
  margin: 0 auto;
}

a {
  text-decoration: none;
  color: $headline-color;
}

svg {
  fill: $headline-color;
}

button {
  background: none;
  outline: none;
  border: 0;
  padding: 2px;
  cursor: pointer;
}

nav {
  float: right;
}

.nav-links {
  max-height: 0;
  transition: max-height 0.35s;
  overflow: hidden;
  position: absolute;
  left: -10vw;
  top: 50px;
  background: #fff;
  flex-direction: column;
  width: 100vw;
  display: flex;

  &.expanded {
    max-height: 50vh;
  }
}
.nav-link {
  height: 50px;
  line-height: 50px;
  padding: 0 10vw;
  border-top: 1px solid rgba(0, 0, 0, 0.1);
}

.feed-subscribe {
  margin-left: 10px;

  svg {
    position: relative;
    top: 4px;
  }
}

@media screen and (min-width: 600px) {
  nav {
    button {
      display: none;
    }
  }
}
</style>


<script>
import variables from 'saber/variables'
import getSvg from '../utils/getSvg'

export default {
  props: {
    siteTitle: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      feedLink: variables.feedLink,
      expanded: false
    }
  },
  methods: {
    getSvg
  }
}
</script>
