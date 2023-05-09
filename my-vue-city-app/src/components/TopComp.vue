<template>
  <header>
      <ul class="gnb">
        <!--  v-값,i-속성명 -->
          <li v-for="(v,i) in this.$store.state.cityData" v-bind:key="i" v-if="i!='인트로'">
              <a href="#" v-on:click="chgData(i)">
                {{ i }}
              </a>
          </li>
      </ul>
      <!-- 메뉴선택이동링크 -->
      <div class="m2">
        <a href="#" v-on:click="chgMenu(num)" v-text="'메뉴'+num"></a>
      </div>
  </header>
</template>

<script>
export default {
  name: 'TopArea',
  data () {
    return {
      // 1. 도시정보 객체변수
      sdata: this.$store.state.cityData,
      // 2. 메뉴번호(처음에 다음메뉴인 2번넣음)
      num: 2
    }
  },
  methods:{
        // 스토어 변수 업데이트 메서드
        chgData(pm){
            console.log("업데이트!",pm);
            // 뮤테이션 메서드 호출하기!
            this.$store.commit('chgData',pm);
        },
        // 메뉴변경하기 메서드
        chgMenu(n){ // n - 메뉴번호전달
          console.log("메뉴변경:",n);
          // 뮤테이션 메서드 호출하기!
          this.$store.commit('chgMenu',n);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.m2{
  display: block;
  text-align: right;
}
.m2 a{
  font-size: 20px;
}
.m2 a:hover{
  text-decoration: underline;
  text-decoration-style: double;
  color: green;
}
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
