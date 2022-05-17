<template>
  <div class="card-container">
    <div class="costum-card">
        <img :src="myCardsItem.poster" :alt="myCardsItem.title">
        <h3>{{myCardsItem.title}}</h3>
        <p>{{myCardsItem.author}}</p>
        <p>{{myCardsItem.year}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "myCards",
  props: {
    myCardsItem: Object
  }
}
</script>

<style lang="scss" scoped>

.costum-card{
  width: 230px;
  min-height: 250px;
  background-color: #2E3A46;
  margin-bottom: 50px;
}

img{
  width: 200px;
  height: 200px;
  margin-left: 15px;
  margin-top: 15px;
}

img,
h3,
p{
  text-align: center;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

h3{
  color: white;
  text-transform: uppercase;
  padding: 10px;
}

p{
  color: #908983;
  padding: 5px;
}

</style>