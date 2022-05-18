<template>
  <main>
    <mySelector class="mySelector" @search="cardToSearch" />
    <div class="w-70">
      <myCards 
      v-for="(music, index) in filterCards" 
      :key="`music-${index}`" 
      :myCardsItem="music"/>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import myCards from "./myCards.vue"
import mySelector from './mySelector.vue';

export default {
  name: "myMain",

  data(){
    return{
      dataURL: "https://flynn.boolean.careers/exercises/api/array/music",
      musics: [],
      cardGenreSearch: "",
      isLoaded: false
    }
  },

  components: {
    myCards,
    mySelector
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
    },

    cardToSearch(cardsOptions){
      console.log(cardsOptions);
      this.cardGenreSearch = cardsOptions
    }
  },

  computed:{
    filterCards(){
      let cardArray = [];

      if(this.cardGenreSearch === "Seleziona un genere"){
        cardArray = this.musics
      } else {
        cardArray = this.musics.filter(cards => {
          return cards.genre.includes(this.cardGenreSearch)
        })
      }

      return cardArray;
    }
  }

}  
</script>

<style lang="scss" scoped>

main{
  background-color: #1E2D3B;
  min-height: 100vh;
}

.mySelector{
  min-height: 10vh;
  background-color: #2E3A46;
  margin-bottom: 50px;
}

div{
  display: flex;
  flex-basis: 20%;
  flex-wrap: wrap;
}

</style>