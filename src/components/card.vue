<template lang="html">
  <!-- Sport -->
  <div class="app" >
    <div class="card width-card" v-show="list.type==='sport'">
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <div class="tapsport">
              <p class="title is-5 text"><i class="fa fa-futbol-o" aria-hidden="true"></i>&nbsp;{{list.type}}( {{list.sport}} )</span></p>
            </div>
          </div>
        </div>
        <div class="content sizefont">
          {{list.competition}}<br>
          {{list.scorepoint}}<br>
          location : {{list.location}}<br>
          <small>{{list.time}}</small>
        </div>
        <button type="button" name="button">-</button>
        <button type="button" name="button">+</button>
        <button type="button" name="button">-</button>
        <button type="button" name="button">+</button><br>
        <button type="button" name="button">Add Set</button>
      </div>
    </div>
    <!-- ส่วนของกิจกรรมต่างๆ -->
    <div class="card width-card" v-show="list.type==='Program'">
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <div class="tapprogram">
              <p class="title is-5 text"><i class="fa fa-list-alt" aria-hidden="true"></i>&nbsp;&nbsp;{{list.type}}</span></p>
            </div>
          </div>
        </div>
        <div class="content sizefont">
          {{list.message}}<br>
          location : {{list.location}}<br>
          <small>{{list.time}}</small>
        </div>
      </div>
    </div>
<!-- รูปภาพ -->
    <div class="card width-card" v-show="list.type==='picture'">
      <div class="card-image">
        <figure class="image is-3by2">
          <img :src="list.picture" alt="">
        </figure>
      </div>
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <div class="tappic">
              <p class="title is-5 text"><i class="fa fa-picture-o" aria-hidden="true"></i>&nbsp;&nbsp;{{list.type}}</span></p>
            </div>
          </div>
        </div>
        <div class="content sizefont">
          {{list.caption}}<br>
          <small>{{list.time}}</small>
        </div>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['list'],
  data () {
    return {
    }
  },
  computed: {},
  mounted () {},
  methods: {},
  components: {
  }
}
</script>

<style lang="css">
.app {
  margin-bottom: 20px;
}


.width-card {
  width: 100%;
  margin-left: 0%;
  margin-right: 0%;
  text-align: center;
  color: pink;
  background-color: #FFFFFF ;
  border-radius: 5px;
  box-shadow: 0px 2px 5px #888888;
}
.text{
  color: white;
}
.sizefont{
  font-size: 17px;
}
.headericon{
  padding-right:70px;
}

.tapicon{
  padding-right: 90px;
}
.tapsport{
  width: 100%;
  background-color:#ff1744 ;
  height: 30px;
  border-radius: 9px;
  padding-top: 5px;
  padding-left: 5px;
  color: white;
}

.tapprogram{
  width: 100%;
  background-color:#ff1744 ;
  height: 30px;
  border-radius: 9px;
  padding-top: 5px;
  padding-left: 5px;
}

.tappic{
  width: 100%;
  background-color:#ff1744;
  height: 30px;
  border-radius: 9px;
  padding-top: 5px;
  padding-left: 5px;
}
</style>
