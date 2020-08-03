<template>
  <header>

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

</style>