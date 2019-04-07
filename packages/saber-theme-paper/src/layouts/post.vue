<template>
  <Wrap :page="page">
    <article class="post typo" itemscope itemtype="http://schema.org/BlogPosting">
      <header class="post-header">
        <h1 class="post-title" itemprop="name headline">{{ page.attributes.title }}</h1>
        <p class="post-meta">
          <time
            class="dt-published"
            :datetime="page.attributes.createdAt"
            itemprop="datePublished"
          >{{ formatDate(page.attributes.createdAt) }}</time>
        </p>
      </header>

      <div class="post-content" itemprop="articleBody">
        <slot name="default"/>
      </div>
      <a class="u-url" :href="page.attributes.permalink" hidden></a>
      <div class="pagination">
        <router-link class="prev" v-if="page.prevPost" :to="page.prevPost.attributes.permalink">
          <strong>{{ $siteConfig.pagination && $siteConfig.pagination.prevPost || '上一篇' }}</strong>
          <p>{{ page.prevPost.attributes.title }}</p>
        </router-link>
        <router-link class="next" v-if="page.nextPost" :to="page.nextPost.attributes.permalink">
          <strong>{{ $siteConfig.pagination && $siteConfig.pagination.nextPost || '下一篇' }}</strong>
          <p>{{ page.nextPost.attributes.title }}</p>
        </router-link>
      </div>
    </article>
    <Disqus
      v-if="page.attributes.comments !== false && $themeConfig.disqus"
      :url="$siteConfig.url"
      :permalink="page.attributes.permalink"
      :shortname="$themeConfig.disqus"
    />
  </Wrap>
</template>

<style lang="scss">
article.typo {
  font-size: 16px;

  a {
    word-break: break-all;
  }

  .pagination {
    display: flex;
    font-size: 14px;
    justify-content: space-between;

    a {
      border-bottom: 0;
      flex: 1;

      &.prev {
        text-align: right;
        padding-right: 10px;
      }
      &.next {
        text-align: left;
        padding-left: 10px;
      }
    }
  }
}
</style>


<script>
import formatDate from '../utils/formatDate'
import Wrap from '../components/Wrap.vue'
import Disqus from '../components/Disqus.vue'

export default {
  components: {
    Wrap,
    Disqus
  },

  props: ['page'],

  methods: {
    formatDate
  }
}
</script>
