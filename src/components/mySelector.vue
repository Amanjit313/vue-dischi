<template>
  <div class="mySelector">

    <div class="logo">
        <i class="fa-brands fa-spotify"></i>
    </div>

    <div class="selector">
      <div class="select">
        <select>
          <option>Seleziona un genere</option>
          <option>Rock</option>
          <option>Pop</option>
          <option>Jazz</option>
          <option>Metal</option>
        </select>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "mySelector"
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