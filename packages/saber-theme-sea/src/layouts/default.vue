<template>
  <Wrap :page="page">
    <div class="home">
      <h1 class="site-title" v-if="$siteConfig.title">{{ $siteConfig.title }}</h1>
      <p class="site-description" v-if="$siteConfig.description">{{ $siteConfig.description }}</p>

      <slot name="default"></slot>

      <h2
        class="post-list-heading"
        v-if="page.posts && page.posts.length > 0"
      >{{ page.attributes.listTitle || 'Articles' }}</h2>

      <ul class="post-list" v-if="page.posts && page.posts.length > 0">
        <li v-for="post in page.posts" :key="post.attributes.permalink">
          <span class="post-meta">{{ formatDate(post.attributes.createdAt) }}</span>
          <h3>
            <saber-link
              class="post-link"
              :to="post.attributes.permalink"
            >{{ post.attributes.title }}</saber-link>
          </h3>
        </li>
      </ul>

      <div
        class="pagination"
        v-if="page.pagination && (page.pagination.hasNext || page.pagination.hasPrev)"
      >
        <router-link
          class="prev-link"
          :to="page.pagination.prevLink"
          v-if="page.pagination.hasPrev"
        >← Previous</router-link>
        <router-link
          class="next-link"
          :to="page.pagination.nextLink"
          v-if="page.pagination.hasNext"
        >Next →</router-link>
      </div>

      <p class="feed-subscribe" v-if="feedLink">
        <svg class="svg-icon orange">
          <use :xlink:href="getSvg('rss')"></use>
        </svg>
        <a :href="feedLink">Subscribe</a>
      </p>
    </div>
  </Wrap>
</template>

<style lang="scss" scoped>
.post-list-heading {
  font-size: 0.6866rem;
  line-height: 1.6rem;
  font-family: IBM Plex Mono, SFMono-Regular, Menlo, Monaco, Consolas,
    Liberation Mono, Courier New, monospace;
  color: rgba(22, 20, 31, 0.4);
  width: 100%;
  font-weight: 400;
  text-transform: uppercase;
}
.post-list {
  list-style: none;
  margin: 0;
  padding: 0;
}
.post-meta {
  color: rgba(98, 146, 241, 0.8);
  opacity: 0.5;
  font-weight: 400;
  display: block;
  font-family: IBM Plex Mono, SFMono-Regular, Menlo, Monaco, Consolas,
    Liberation Mono, Courier New, monospace;
  text-transform: uppercase;
  font-size: 0.6866rem;
  line-height: 1.6rem;
}
.post-link {
  font-size: 1rem;
  line-height: 1.2;
  color: #333;
  background: transparent;
  box-shadow: none;
  font-family: Spectral, Georgia, serif;
  font-weight: 400;
  padding-left: 0;
  text-shadow: none;
  position: relative;
  text-decoration: none;

  &:hover {
    // background: rgba(98, 146, 241, 0.3);
    color: #6292f1;
    &::before {
      width: 280px;
      left: -300px;
    }
  }

  &::before {
    content: ' ';
    position: absolute;
    top: 10px;
    left: -20px;
    width: 4px;
    height: 4px;
    border-radius: 2px;
    background: #6292f1;
    transition: all 200ms cubic-bezier(0.4, 0, 1, 1);
  }
}
</style>


<script>
import variables from 'saber/variables'
import formatDate from '../utils/formatDate'
import Wrap from '../components/Wrap.vue'
import getSvg from '../utils/getSvg'

export default {
  components: {
    Wrap
  },

  props: ['page'],

  data() {
    return {
      feedLink: variables.feedLink
    }
  },

  methods: {
    formatDate,
    getSvg
  }
}
</script>
