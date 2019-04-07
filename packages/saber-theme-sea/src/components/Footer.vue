<template>
  <footer class="footer">
    <p>{{ $siteConfig.footerAnnotation }}</p>
    <p class="copyright">
      Powered by
      <a class="power" href="https://saberjs.org">Saber</a>, theme
      <a class="theme" href="https://github.com/geekplux/saber-theme-typing">Typing</a>
    </p>
  </footer>
</template>

<style lang="scss" scoped>
@import '../styles/variables.scss';
footer {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  padding: 30px 0;
}

.copyright {
  font-size: 12px;
  color: $gray-light;

  a {
    color: $gray;
  }
}
</style>


<script>
export default {}
</script>
