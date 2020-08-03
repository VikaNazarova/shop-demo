<template>
  <div>
      <h1>{{service.name}}</h1>
      <!-- <img :src="'http://localhost:1337'+service.thumbnail.url" :alt="service.name"> -->
      <div>{{service.description}}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      service: {}
    };
  },
  created() {
    fetch(`http://localhost:1337/services/?url=${this.$route.params.url}`)
	  .then(res => res.json())
    .then(service => {
     this.service = service[0];
    })
	.catch(err => console.log(err));
  },
  head() {
    return {
      title: this.service.meta_title,
      meta: [
        {
          hid: "description",
          name: "description",
          content: this.service.meta_description
        },
        {
          hid: "keywords",
          name: "keywords",
          content: this.service.meta_keywords
        }
      ]
    };
  }
};
</script>

<style>

</style>
