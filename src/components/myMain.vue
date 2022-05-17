<template>
  <main>
    <div class="w-70">
      <myCards 
      v-for="(music, index) in musics" 
      :key="`music-${index}`" 
      :myCardsItem="music"/>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import myCards from "./myCards.vue"

export default {
  name: "myMain",
  data(){
    return{
      dataURL: "https://flynn.boolean.careers/exercises/api/array/music",
      musics: [],
      isLoaded: false
    }
  },
  components: {
    myCards,
  },
  
  mounted(){
    this.getAPI()
  },

  methods:{
    getAPI(){
     axios.get(this.dataURL)
     .then(r => {
        this.musics = r.data.response;
        console.log(this.musics.response)
        this.isLoaded = true
     })
    }
  }
}
</script>

<style lang="scss" scoped>

main{
  background-color: #1E2D3B;
}

div{
  display: flex;
  flex-basis: 20%;
  flex-wrap: wrap;
}

</style>