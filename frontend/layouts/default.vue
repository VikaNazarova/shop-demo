<template>
  <div>
    <appHeader />
    <Nuxt />
    <appFooter />
  </div>
</template>

<script>
import AppHeader from "../components/AppHeader";
import AppFooter from "../components/AppFooter";
export default {
  components: {
    AppHeader,
    AppFooter
  }
};
</script>

<style>
:root {
  font-size: 16px;
  font-family: Helvetica, sans-serif;
  }
  body {
    margin: 0;
  }
  a {
    text-decoration: none;
  }
  a:hover {
    filter: invert(100%);
  }
  h1 {
    font-size: 4rem;
    margin-top: 0;
  }
  h2 {
    font-size: 3rem;
    text-align: center;
  }
  h3 {
    font-size: 2.25rem;
  }
  p {
    font-size: 1.125rem;
  }
  button {
    font-size: 1.125rem;
    color: #fff;
    border: none;
    border-radius: 0;
    padding: 1rem 2rem;
    background: #007bff;
  }
  button:hover {
    cursor: pointer;
    color: #007bff;
    background: #fff;
  }
  .module {
    margin: 3rem 0;
  }
  .container {
    width: 70vw;
    margin: 0 auto;
  }
</style>
