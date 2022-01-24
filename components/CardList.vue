<template>
  <div class='card-list'>
    <div class='card'>
      <!-- header -->
      <div class='card-header'>
        <img src='' alt=''>
      </div>
      <!-- description -->
      <div class='card-info'></div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CardList',
  data() {
    return {
      list: [
        {
          name: ''
        }
      ],
    }
  }
}
</script>
<style lang='scss' scoped>
.card-list {
  .card {
    width: 300px;
    height: 80px;
  }
}
</style>
