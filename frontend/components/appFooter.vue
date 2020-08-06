<template>
  <footer>
    <div class="column">
        <nuxt-link to="/">
            <img src="../static/logo.png" alt="">
        </nuxt-link>
        <p style="font-weight: bold;">{{info.organization}}</p>
        <p>Paragraph about something cool</p>
    </div>

    <div class="column">
      <nav v-for="page in pages"  :key="page.id">
        <nuxt-link :to="`${page.url}`">{{page.name}}</nuxt-link>
      </nav>
    </div>

    <div class="column">
        <nav v-for="service in services"  :key="service.id">
            <nuxt-link :to="`/services/${service.url}`">{{service.name}}</nuxt-link>
        </nav>
    </div>

    <div class="column">
        <p style="font-weight: bold;">{{info.organization}}</p>
        <a href="`tel:${info.telephone}`">{{info.telephone}}</a>
        <a href="`mailto:${info.email}`">{{info.email}}</a>
        <p><span>{{info.postalCode}}, </span>
        <span>{{info.addressRegion}}, </span>
        <span>{{info.addressLocality}}, </span>
        <span>{{info.streetAddress}}</span></p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
  data() {
    return {
      info: [],
      pages: [],
      services: []
    };
  },
  created() {
    fetch('http://localhost:1337/info')
	.then(res =>  res.json())
    .then(info => {
     this.info = info;
    })
    .catch(err => console.log(err));
      
    fetch('http://localhost:1337/pages')
	.then(res =>  res.json())
    .then(pages => {
     this.pages = pages;
    })
    .catch(err => console.log(err));
    
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
  footer {
    display: flex;
    justify-content: space-between;
    background: #6c757d;
    padding: 5rem;
  }
  footer .column {
    flex: 1 1 auto;
  }
  footer a {
    display: block;
    font-size: 1.125rem;
    color: #000;
    padding: 1rem 0;
  }
</style>