<template>
  <header>
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
    </nav>
  </header>
</template>

<style lang="scss" scoped>
header {
  height: 50px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 0 10vw;
  background: #6292f1;
  color: #fff;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 1px 3px 0px;
  position: relative;
}

a {
  text-decoration: none;
  color: #fff;
}

svg {
  fill: #fff;
}

button {
  background: none;
  outline: none;
  border: 0;
  padding: 2px;
}

nav {
  float: right;
}

.nav-links {
  max-height: 0;
  transition: max-height 0.35s;
  overflow: hidden;
  position: absolute;
  left: 0;
  top: 50px;
  background: #6292f1;
  flex-direction: column;
  width: 100%;
  display: flex;

  &.expanded {
    max-height: 50vh;
  }
}
.nav-link {
  height: 50px;
  line-height: 50px;
  padding: 0 30px;
  border-top: 1px solid rgba(255, 255, 255, .3);
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
export default {
  props: {
    siteTitle: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      expanded: false
    }
  }
}
</script>
