<template>
  <div class="mySelector">

    <div class="logo">
        <i class="fa-brands fa-spotify"></i>
    </div>

    <div class="selector">
      <div class="select">
        <select v-model="cardSearch" @change="$emit('search', cardSearch)">
          <option value="Seleziona un genere">Seleziona un genere</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Jazz">Jazz</option>
          <option value="Metal">Metal</option>
        </select>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "mySelector",
  data(){
    return{
      cardSearch: "Seleziona un genere"
    }
  }
}

</script>

<style lang="scss" scoped>

.mySelector{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 40px;
}

.logo{
  color: #35D05B;
  font-size: 3rem;
}

select{
  font-size: 1rem;
  height: 2.5rem;
}

</style>