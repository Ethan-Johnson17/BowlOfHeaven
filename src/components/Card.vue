<template>
  <div class="card mx-2 my-3" v-if="bowl">
    <img v-if="bowl.imgSrc" :src="'../src/assets/img/' + bowl.imgSrc + 'Bowl.jpg'" :alt="bowl.imgSrc" class="menu-item-image">
    <img v-else src="https://placehold.co/900x900?text=Image+Coming+Soon" :alt="bowl.imgSrc" class="menu-item-image">
    <div class="card-body">
      <div class="card-text">
          <h5 class="text-center">{{ bowl.name }}</h5>
          <p class="text-center">SM {{ bowl.SM }} | MED {{ bowl.REG }} | LG {{ bowl.LG }} | XL {{ bowl.SHREK }}</p>
          <p>Blend: {{ bowl.blend }}</p>
          <p>Toppings: {{ bowl.toppings }}</p>
      </div>    
    </div>
  </div>
  <div class="card mx-2 my-3" v-else-if="blast">
    <img v-if="blast.imgSrc" :src="'../src/assets/img/' + blast.imgSrc + 'Blast.jpg'" :alt="blast.imgSrc" class="menu-item-image">
    <img v-else src="https://placehold.co/900x900?text=Image+Coming+Soon" :alt="blast.imgSrc" class="menu-item-image">
    <div class="card-body">
      <div class="card-text">
          <h5 class="text-center">{{ blast.name }}</h5>
          <p class="text-center">SM {{ blast.SM }} | REG {{ blast.REG }} | LG {{ blast.LG }} | XL {{ blast.SHREK }}</p>
          <p>Ingredients: {{ blast.ingredients }}</p>
      </div>    
    </div>
  </div>
  <div class="card mx-2 my-3" v-else-if="soup">
    <img v-if="soup.imgSrc" :src="'../src/assets/img/' + soup.imgSrc + '.jpg'" :alt="soup.imgSrc" class="menu-item-image">
    <img v-else src="https://placehold.co/900x900?text=Image+Coming+Soon" :alt="soup.imgSrc" class="menu-item-image">
    <div class="card-body">
      <div class="card-text">
          <h5 class="text-center">{{ soup.name }}</h5>
          <p class="text-center">12 OZ $6.75</p>
          <p>Ingredients: {{ soup.ingredients }}</p>
          <p>Allergens: {{ soup.allergens }}</p>
      </div>    
    </div>
  </div>
  <div class="card mx-2 my-3" v-else-if="drink">
    <img v-if="drink.imgSrc" :src="'../src/assets/img/' + drink.imgSrc + '.jpg'" :alt="drink.imgSrc" class="menu-item-image">
    <img v-else src="https://placehold.co/900x900?text=Image+Coming+Soon" :alt="drink.imgSrc" class="menu-item-image">
    <div class="card-body">
      <div class="card-text-small">
          <h5 class="text-center">{{ drink.name }}</h5>
          <p class="text-center">{{ drink.price }}</p>
      </div>    
    </div>
  </div>

</template>

<script>
export default {
  props: {
    bowl: {
      type: Object
    },
    blast: {
      type: Object
    },
    soup: {
      type: Object
    },
    drink: {
      type: Object
    }
  },
  setup(props) {
    return {

    }
  }
}
</script>

<style>
.card {
  transition: 500ms;
  background-color: #fffaf3;
}

.card:hover {
  scale: 120%;
  z-index: 400;
  transition: 500ms;
}

.card-image {
  /* height: 15rem; */
}

.card-text {
  height: 200px;
}

.card-text-small {
  height: 75px;
}

.menu-item-image {
  /* height: 200px;
  width: 200px; */
  background-size: cover;
}
</style>