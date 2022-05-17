<template>
  <div>
    MAIN
  </div>
</template>

<script>
import axios from "axios";

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
  
  },
  
  mounted(){
    this.getAPI()
  },

  methods:{
    getAPI(){
     axios.get(this.dataURL)
     .then(r => {
        this.musics = r.data;
        this.isLoaded = true
     })
    }
  }
}
</script>

<style>

</style>