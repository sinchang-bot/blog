<template>
  <header>
    <div class="header">
      <saber-link class="domain" rel="domain" to="/">{{ $siteConfig.domain }}</saber-link>
      <nav class="info">
        <div class="site-info">
          <saber-link class="title" rel="author" to="/">{{ $siteConfig.title }}</saber-link>
          <p class="description">{{ $siteConfig.description }}</p>
          <div :class="{expanded: expanded}" class="nav-links" v-if="$themeConfig.nav">
            <saber-link
              :key="index"
              class="nav-link"
              v-for="(navItem, index) in $themeConfig.nav"
              :to="navItem.link"
            >{{ navItem.text }}</saber-link>
          </div>
        </div>
        <div class="author-info">
          <img v-if="$siteConfig.avatar" class="avatar" :src="$siteConfig.avatar">
          <Social/>
        </div>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import '../styles/variables.scss';

header {
  padding: 0 10vw;
}

.domain {
  font-size: 14px;
  font-style: italic;
  font-weight: 300;
  color: $gray-light;
  padding: 80px 0;
  display: block;
}

.title {
  font-weight: bold;
  font-size: 1.5em;
}

.description {
  font-size: 16px;
  color: $gray;
}

.nav-links {
  font-size: 16px;
  font-style: italic;
  a {
    margin-right: 10px;
    border-bottom: 1px solid $gray-light;
  }
}

.avatar {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  border: 3px solid #fff;
  transition: transform 1s;
  animation: fade-in-down 0.6s;
  animation-delay: 0.2s;

  &:hover {
    transform: rotate(-360deg);
  }
}

.author-info {
  position: absolute;
  top: 30px;
  right: 10vw;
  text-align: right;
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
import Social from './Social.vue'

export default {
  components: {
    Social
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
