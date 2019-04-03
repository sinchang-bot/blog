<template>
  <nav>
    <h1>My Blog</h1>
    <ul>
      <li>
        <saber-link to="/">Home</saber-link>
      </li>
      <li>
        <saber-link to="/about.html">About me</saber-link>
      </li>
    </ul>
  </nav>
</template>

<style scoped>

nav {
  display: flex;
  height: 30px;
  align-items: center;
  border-bottom: 3px solid #f0f0f0;
}
</style>