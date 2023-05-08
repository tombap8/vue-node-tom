<template>
  <header>
      <ul class="gnb">
          <li>
              <a href="#" v-on:click="chgData('서울')">서울</a>
          </li>
          <li>
              <a href="#" v-on:click="chgData('부산')">부산</a>
          </li>
          <li>
              <a href="#" v-on:click="chgData('제주')">제주</a>
          </li>
      </ul>
  </header>
</template>

<script>
export default {
  name: 'TopArea',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
    padding: 15px;
    border: 2px solid #ccc;
}
header ul {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 0 15px;
}
header a {
    font-size: 30px;
    color: #222;
    text-decoration: none;
}
header a:hover,
header a.on {
    color: orangered;
    text-decoration: overline;
    text-decoration-style: wavy;
}
</style>
