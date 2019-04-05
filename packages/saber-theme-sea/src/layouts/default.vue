<template>
  <Wrap :page="page">
    <div class="home">
      <!-- <h1 class="site-title" v-if="$siteConfig.title">{{ $siteConfig.title }}</h1>
      <p class="site-description" v-if="$siteConfig.description">{{ $siteConfig.description }}</p>
      -->
      <slot name="default"></slot>

      <h2
        class="post-list-heading"
        v-if="page.posts && page.posts.length > 0"
      >{{ page.attributes.listTitle || '博客' }}</h2>

      <ul class="post-list" v-if="page.posts && page.posts.length > 0">
        <li class="post" v-for="post in page.posts" :key="post.attributes.permalink">
          <span class="post-meta">
            <span class="date">{{ formatDate(post.attributes.createdAt) }}</span>
            <span
              class="categories"
              v-for="category in post.attributes.categories"
              :key="category.toString()"
            >, {{category}}</span>
          </span>
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
    </div>
  </Wrap>
</template>

<style lang="scss" scoped>
.post-list-heading {
  color: #888;
  font-weight: lighter;
  margin-bottom: 50px;
}
.post-list {
  list-style: none;
  margin: 0;
  padding: 0;
}
.post {
  margin-bottom: 2em;
}
.post-meta {
  display: block;
  color: #bbb;
  font-size: 12px;
  font-style: italic;
  font-weight: lighter;
}
.post-link {
  position: relative;
  text-decoration: none;
  color: #1f1f1f;
  font-size: 20px;

  &:hover {
    // background: rgba(98, 146, 241, 0.3);
    color: #1f1f1f;
    &::before {
      width: 20px;
      left: -40px;
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
    background: #1f1f1f;
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
