<template>
  <div class="card">
    <img :src="card.image" alt="" /><!-- propsdan gelen datani gostermek ucun yeni hansi attributa tesir edecek bu data hemin attributi active etmek ucun : bindingden istifade olunur -->
  </div>
</template>

<script>
  export default{
    props:['card']
  }
</script>

<style scoped>
  .card {
    width: 200px;
    height: 232px;
    border: 1px solid #666;
    border-radius: 5px;
    transition: box-shadow 1s; /* burdaki transtion kodu hover deactive olanda isleyir */
    margin: auto;
  }
  .card:hover {
    box-shadow: 0px 5px 48px #666;
    transition: box-shadow 0.5s;
  }
  .card img {
    width: 100%;
    height: 100%;
  }

  .card:first-child{
    margin-left: 0px;
  }

</style>
