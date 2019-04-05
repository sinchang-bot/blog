<template>
  <div class="home">
    <div class="author">
      <h1>{{$siteConfig.title}}</h1>
    </div>
    <p class="p-name">{{ $siteConfig.author ? $siteConfig.author : siteTitle }}</p>
    <p>{{ $siteConfig.description }}</p>
  </div>
</template>

<style lang="scss" scoped>
.home {
  background: url('../public/bg.jpg') no-repeat center center;
  color: #fff;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>