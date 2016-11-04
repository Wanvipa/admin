<template>
  <div class="body" >
    <show :lists="lists" :add-event="addEvent"></show>
  </div>
</template>

<script>
import firebase from 'firebase'
// Initialize Firebase
var config = {
  apiKey: 'AIzaSyBasyXEYg3xGN6Y9ndOtt9chPV4m60_6Xw',
  authDomain: 'it-3k-1f766.firebaseapp.com',
  databaseURL: 'https://it-3k-1f766.firebaseio.com',
  storageBucket: 'it-3k-1f766.appspot.com',
  messagingSenderId: '914467199924'
}
firebase.initializeApp(config)
var It3k = firebase.database().ref('It3k')
import Show from './components/Show'
export default {
  components: {
    Show
  },
  data () {
    return {
      lists: []
    }
  },
  mounted () {
    var vm = this
    It3k.on('child_added', function (snapshot) {
      var item = snapshot.val()
      item.id = snapshot.key
      vm.lists.splice(0, 0, item)
    })
    It3k.on('child_removed', function (snapshot) {
      var id = snapshot.key
      var index = vm.lists.findIndex(lists => lists.id === id)
      vm.lists.splice(index, 1)
    })
    It3k.on('child_changed', function (snapshot) {
      // var id = snapshot.key
      // var listIt3k = vm.lists.find(list => list.id === id)
      console.log(snapshot.val())
    })
  },
  methods: {
    addEvent (item) {
      It3k.push(item)
    }
  }
}
</script>
<style lang="css">
@import url('https://fonts.googleapis.com/css?family=Athiti|Sriracha&subset=thai');
body {
  background-color:#fff;
  /*background-image:url('./BG.jpg');*/
  /*border-style: solid;*/
  /*border-color:white ;*/
  /*border-width: 5px;*/
  font-family: 'Athiti', sans-serif;
  font-family: 'Sriracha', cursive;
  /*font-size: 10%;*/
}

</style>
