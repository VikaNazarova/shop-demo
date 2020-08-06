<template>
  <header>
    <div>
      <nuxt-link to="/">
        <img src="../static/logo.png" alt="">
      </nuxt-link>
    </div>
    <div>
      <a style="font-weight: bold;" href="tel:+7000000000">+7 (000) 00 00 00</a>
    </div>
    <div>
      <nav v-for="page in pages"  :key="page.id">
        <nuxt-link :to="`${page.url}`">{{page.name}}</nuxt-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      pages: []
    };
  },
  created() {
    fetch('http://localhost:1337/pages')
	  .then(res =>  res.json())
    .then(pages => {
     this.pages = pages;
    })
	  .catch(err => console.log(err));
  },
};
</script>

<style>
  header {
    display: flex;
    height: 5rem;
    background: #007bff;
    justify-content: space-between;
  }
  header div {
    display: flex;
    align-items: center;
  }
  header a {
    font-size: 	1.125rem;
    color: #fff;
    padding: 2rem;
  }
</style>