<template lang="html">
  <div>
      <div id="header">
        <span class="icon is-medium" @click="home">
        <i class="fa fa-home"></i>
        </span>
        <span class="icon is-medium" @click="inputData = !inputData">
          <i class="fa fa-keyboard-o" aria-hidden="true"></i>
        </span>
      </div>

    <div class="column">
      <h3 class="tital subtitle is-3">IT3K-13th: Night Life 2016</h3>
      </div>
      <div class="column" v-show="!inputData">
      <cards  :list="list" v-for="list in lists" ></cards>
      </div>
      <div class="column" v-show="inputData">
        <fromInput :add-event="addEvent"></fromInput>
      </div>
      <div class="column"></div>

  </div>

</template>

<script>
import Cards from './Card'
import fromInput from './Add'
export default {
  props: ['lists', 'addEvent'],
  data () {
    return {
      inputData: false
    }
  },
  computed: {},
  mounted () {},
  methods: {
    home () {
      window.scrollTo(0, 0)
    }
  },
  components: {
    Cards,
    fromInput
  }
}
</script>

<style lang="css">
h3 {
    text-align: center;
    /*color: #3f51b5;*/
    margin-top: 55px;
}
.tital{
  color:gray;
  text-shadow: white 0.1em 0.1em 0.2em;
}
.tap{
  width: 100%;
}
#header {
  position: fixed;
  width: 100%;
  margin-left: 0%;
  margin-right: 0%;
  display: inline-block;
  background:#ff5252;
  padding: 10px;
  font-variant: small-caps;
  font-weight: bold;
  color: #fff;
  box-shadow: 0 0 5px #000;
  z-index: 999;
}

</style>
