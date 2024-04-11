<template>
  <table class="table">
    <tr class="d-table-row">
      <td class="d-table-cell">Название</td>
      <td class="d-table-cell">{{product.title}}</td>
    </tr>
    <tr class="d-table-row">
      <td class="d-table-cell">Фотка</td>
      <td class="d-table-cell"><img class="img-fluid" :src="product.images[0]" alt=""></td>
    </tr>
    <tr class="d-table-row">
      <td class="d-table-cell">Описание</td>
      <td class="d-table-cell">{{product.description}}</td>
    </tr>
    <tr class="d-table-row">
      <td class="d-table-cell">Рейтинг</td>
      <td class="d-table-cell">{{product.rating}}</td>
    </tr>
    <tr class="d-table-row">
      <td class="d-table-cell">Цена</td>
      <td class="d-table-cell">{{product.price}}</td>
    </tr>
  </table>

</template>

<script>

  export default {
    data() {
      return {
        product: null,
      }
    },
    created() {
      const id = this.$route.params.id
      const url = 'https://dummyjson.com/products/' + id;
      fetch(url)
          .then(response => response.json())
          .then( data = this.products = data)
    }
  }
</script>
