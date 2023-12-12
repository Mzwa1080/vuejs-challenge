<template>
  <!-- then you call the valu or u use the value in the vurron when its selected it must call the computed -->

  <!-- so u must also have a filter that when the drop down is selected. i am able to get the value by the name -->

  <!-- I must have a search that will search through the products by name and display nothing if there's nothing -->
<div class="container">
  <div class="row" v-if="products.length">
  <div class="dropdown">
    <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
      Select An Item
    </button>
    <ul class="dropdown-menu">
      <li v-for="item in products" :key="item.id">
        <a class="dropdown-item" href="#" @click="uniqueCategories(item)">
          {{ item.brandName }}
        </a>
      </li>
    </ul>
  </div>
</div>

<div class="row mt-3" >
  <div   class="card" v-for="filteredItem in filteredProducts" :key="filteredItem.id" style="width: 14rem;">
  <img :src="filteredItem.img" class="card-img-top" :alt="filteredItem.brandName">
  <div class="card-body">
    <h5 class="card-title">{{filteredItem.brandName}}</h5>
    <a href="#" class="btn btn-primary">R{{filteredItem.price}}</a>
  </div>
</div>
</div>

</div>


</template>

<script>

export default {
  name: 'App',
  components: {},
  data() {
    return {
      products: [
        {
          id: 1,
          img: 'https://i.postimg.cc/zDx4dPyh/image-2.png',
          brandName: 'nike',
          description: 'NIKE AIR FORCE 1 LV8',
          price: '2000',
        },
        {
          id: 2,
          img: 'https://i.postimg.cc/jjp7FYSy/Screenshot-2023-12-06-092205.pngg',
          brandName: 'adidas',
          description: 'ROADRUNNER  ',
          price: '3000',
        },
        {
          id: 3,
          img: 'https://i.postimg.cc/sg0S5hF6/Screenshot-2023-12-06-092049.png',
          brandName: 'Yeezy',
          description: 'WALK IN THE OCEAN',
          price: '1800',
        },
        {
          id: 4,
          img: 'https://i.postimg.cc/D0Q1TJwy/image-8.png',
          brandName: 'nike',
          description: 'NIKE  AIR FORCE 1 ‘07 WB',
          price: '2400',
        },
        {
          id: 5,
          img: 'https://i.postimg.cc/JzhZyQFH/Screenshot-2023-12-06-092228.png',
          brandName: 'lacoste',
          description: 'L-GUARD BREAKER CT TEXTILE',
          price: '1800',
        }

      ],
      filteredProducts : [],
    }
  },

  methods : {
    uniqueCategories(value){

        console.log(value);
        this.filteredProducts.push(value)

    }
  },

  // computed: {
  //   uniqueCategories(value) {
  //     console.log(value);
  //     return value
  //   }
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}


</style>
