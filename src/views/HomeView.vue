<template>
  <body class="home-bg">
    <div class="home">
      <img alt="Vue logo" src="../assets/logo.png" />
      <HelloWorld msg="Welcome to Your Vue.js App" />
    </div>
  </body>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
  },
};
</script>

<style>
html {
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

/* set background image per page */
.home-bg {
  background: url("https://static.clubs.nfl.com/image/private/t_editorial_landscape_12_desktop/f_auto/eagles/eooxk09lndfv5h5jclpq.jpg"),
    no-repeat center center fixed;
  background-size: cover;
}
.about-bg {
  background-color: darkgreen;
}
</style>
