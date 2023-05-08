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
  },
  methods:{
        // 스토어 변수 업데이트 메서드
        chgData(pm){
            console.log("업데이트!",pm);
            // 이자리에서 바로 스토어 변수를 업데이트 한다!!
            // 1. 이미지 변수 : imgsrc
            this.$store.state.imgsrc = this.$store.state.cityData[pm].이미지;
            // 2. 도시설명 변수 : desc
            this.$store.state.desc = this.$store.state.cityData[pm].설명;

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
