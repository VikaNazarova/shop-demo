<template>
  <div id="hero">
      <div class="container">
        <img src="../static/hero.png" alt="">
        <div class="wrapper">
            <h1>Some kinda <br>
                headline</h1>
                <p>Paragraph about something cool</p>
                <button>Call to action</button>
            </div>
        </div>
  </div>
</template>

<script>
export default {
  name: "hero"
};
</script>

<style>
    #hero {
        background: #e1e4e6;
        padding: 2.8125rem 0;
    }
    #hero .container {
        display: flex;
    }
    #hero .wrapper {
        flex-direction: column;
        margin-left: 5rem;
    }
    #hero button {
        margin-top: 2rem;
    }
</style>