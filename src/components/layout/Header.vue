//Otsikkotason
<template>
  <header class="header">
    <h1>Vue-muistio</h1>
    <div id="nav">
      <router-link to="/">Etusivu</router-link> |
      <router-link to="/about">Lisätietoa</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

//
<style scoped>
  .header {
    background: linear-gradient(-90deg, #84CF6A, #16C0B0);
    color: #fff;
    text-align: center;
    padding: 10px;
  }
  .header a {
    color: #fff;
    padding-right: 5px;
    text-decoration: none;
  }
</style>