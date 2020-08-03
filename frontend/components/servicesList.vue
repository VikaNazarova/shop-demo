<template>
  <div>
    <h2>Our Services</h2>
    <div v-for="service in services" :key="service.id">
        <nuxt-link :to="`/services/${service.url}`">
            <img :src="'http://localhost:1337'+service.thumbnail['url']" :alt="service.name">
            <h3>{{service.name}}</h3>
            <p>{{service.description}}</p>
        </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "servicesList",
  data() {
    return {
      services: []
    };
  },
  created() {
    fetch('http://localhost:1337/services')
	  .then(res =>  res.json())
    .then(services => {
     this.services = services;
    })
	  .catch(err => console.log(err));
  },
};
</script>

<style>

</style>