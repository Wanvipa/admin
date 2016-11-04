<template lang="html">
  <div class="">
    type : <input type="text" name="name" width="100" value="" v-model="type"><br><br>
    time : <input type="text" name="name" value="" v-model="time"><br><br>
    picture : <input type="text" name="name" value="" v-model="picture"><br><br>
    caption : <input type="text" name="name" value="" v-model="caption "><br><br>
    <button @click="add">Add</button>
  </div>
</template>

<script>
export default {
  props: ['addEvent'],
  data () {
    return {
      type: '',
      time: '',
      picture: '',
      caption: ''
    }
  },
  computed: {},
  mounted () {},
  methods: {
    add () {
      var data = {
        type: this.type,
        time: this.time,
        picture: this.picture,
        caption: this.caption
      }
      this.addEvent(data)
      this.type = ''
      this.time = ''
      this.picture = ''
      this.caption = ''
    }
  },
  components: {}
}
</script>

<style lang="css">
</style>
