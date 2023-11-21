<template>
  <div class="container-fluid pt-3">
      <h2>Bowls</h2>
      <div class="row d-flex justify-content-center px-4">
        <div class="col-md-3"  v-for="bowl in bowls" :key="bowl.name" >
          <Card :bowl="bowl" />
        </div>
      </div>
      <div class="row">
        <h2>Blasts</h2>
        <div class="row d-flex justify-content-center px-4">
          <div class="col-md-3"  v-for="blast in blasts" :key="blast.name" >
            <Card :blast="blast" />
          </div>
        </div>
      </div>
      <div class="row">
        <h2>Soups</h2>
        <div class="row d-flex justify-content-center px-4">
          <div class="col-md-3"  v-for="soup in soups" :key="soup.name" >
            <Card :soup="soup" />
          </div>
        </div>
      </div>
      <div class="row">
        <h2>Coffee and Other Drinks</h2>
        <div class="row d-flex justify-content-center px-4">
          <div class="col-md-3"  v-for="drink in drinks" :key="drink.name" >
            <Card :drink="drink" />
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  setup() {
    let bowls = [
      {
        name: 'PEANUT BUTTER PASSION',
        SM: 6.95, REG: 9.95, LG: 12.95, SHREK: 19.50,
        blend: 'Açaí, Peanut Butter, Strawberry, Blueberry, Banana, Chocolate Almond Milk',
        toppings: 'Granola, Dark Chocolate Pieces, Banana, Strawberry, Honey',
        imgSrc: 'PeanutButterPassion'
      },
      {
        name: 'NORTH SHORE ORIGINAL',
        SM: 6.75, REG: 9.75, LG: 12.75, SHREK: 18.50,
        blend: 'Açaí, Strawberry, Blueberry, Banana, Apple Juice',
        toppings: 'Granola, Banana, Strawberry, Blueberry, Honey',
        imgSrc: 'NorthShore'
      },
      {
        name: 'TROPICAL',
        SM: 6.75, REG: 9.75, LG: 12.75, SHREK: 18.50,
        blend: 'Açaí, Pineapple, Strawberry, Blueberry, Banana, Apple Juice',
        toppings: 'Granola, Banana, Strawberry, Pineapple, Honey, Unsweetened Coconut',
        imgSrc: 'Tropical'
      },
      {
        name: 'MANGO TANGO',
        SM: 6.75, REG: 9.75, LG: 12.75, SHREK: 18.50,
        blend: 'Açaí, Mango, Strawberry, Blueberry, Banana, Apple Juice',
        toppings: 'Granola, Banana, Strawberry, Mango, Honey',
        imgSrc: 'Mango'
      },
      {
        name: 'GREENS & THINGS',
        SM: 6.75, REG: 9.75, LG: 12.50, SHREK: 18.50,
        blend: 'Açaí, Spinach, Strawberry, Blueberry, Banana, Apple Juice',
        toppings: 'Granola, Banana, Strawberry, Blueberry, Honey',
        imgSrc: 'GreensAndThings'
      },
      {
        name: 'POPEYE',
        SM: 6.95, REG: 9.95, LG: 12.95, SHREK: 18.50,
        blend: 'Açaí, Spinach, Kale, Strawberry, Blueberry, Banana, Pineapple, Apple Juice',
        toppings: 'Granola, Strawberry, Banana, Blueberry, Pineapple, Honey',
        imgSrc: 'Popeye'
      },
      {
        name: 'ALOHA',
        SM: 6.95, REG: 9.95, LG: 12.95, SHREK: 19.50,
        blend: 'Pitaya, Almond Butter, Strawberry, Banana, Vanilla Almond Milk',
        toppings: 'Granola, Dark Chocolate Pieces, Banana, Strawberry, Honey',
        imgSrc: 'Aloha'
      },
      {
        name: 'RED ZINGER',
        SM: 6.95, REG: 9.95, LG: 12.95, SHREK: 19.50,
        blend: 'Açaí, Ginger, Lime, Blueberry, Pineapple, Mango, Raspberry, Coconut Water',
        toppings: 'Granola, Dark Chocolate Pieces, Raspberry, Honey',
        imgSrc: 'RedZinger'
      },
      {
        name: 'KETO BOWL',
        SM: 6.95, REG: 9.95, LG: 12.95, SHREK: 19.50,
        blend: 'Almond Butter, MCT Oil, Collagen, Spinach, Stevita, Blueberry, Raspberry, Vanilla Almond Milk',
        toppings: 'Pecan, Blueberry, Strawberry, Raspberry',
        imgSrc: 'Keto'
      },
      // {
      //   name: 'BRENT-O-SAURUS (WHEN AVAILABLE)',
      //   SM: 5.75, REG: 8.75, LG: 11.50,
      //   blend: 'Absolute Mystery!',
      //   toppings: 'Granola, Banana, Strawberry, Blueberry, Honey',
      //   imgSrc: 'BrentOSaurus'
      // },

    ]
    let blasts = [
      {
        name: 'BERRY BLAST', SM: 8.75, LG: 11.75,
        ingredients: 'Açaí, Apple Juice, Strawberry, Blueberry, Banana',
        imgSrc: ''
      },
      {
        name: 'TROPICAL', SM: 8.75, LG: 11.75,
        ingredients: 'Açaí, Pineapple, Blueberry, Strawberry, Banana, Apple Juice'
      },
      {
        name: 'MANGO TANGO', SM: 8.75, LG: 11.75,
        ingredients: 'Açaí, Mango, Strawberry, Blueberry, Banana, Apple Juice'
      },
      {
        name: 'GREENS & THINGS', SM: 8.75, LG: 11.75,
        ingredients: 'Açaí, Spinach, Strawberry, Blueberry, Banana, Apple Juice'
      },
      {
        name: 'POPEYE', SM: 8.95, LG: 11.95,
        ingredients: 'Açaí, Spinach, Kale, Strawberry, Blueberry, Banana, Pineapple,'
      },
      {
        name: 'PEANUT BUTTER BLAST', SM: 8.95, LG: 11.95,
        ingredients: 'Açaí, Peanut Butter, Strawberry, Blueberry, Banana, Chocolate Almond Milk'
      },      
      {
        name: 'ALOHA', SM: 8.95, LG: 11.95,
        ingredients: 'Pitaya, Almond Butter, Strawberry, Banana, Vanilla Almond Milk'
      },
      {
        name: 'RED ZINGER', SM: 8.95, LG: 11.95,
        ingredients: 'Açaí, Ginger, Lime, Blueberries, Pineapple, Răspberries, Coconut Water'
      },
      {
        name: 'LEAN GREEN PROTEIN', LG: 10.95,
        ingredients: 'Spinach, 22g Plant Protein, Strawberry, Kangen Water'
      }

    ]
    let soups = [
      {
        name: 'ROASTED RED PEPPER',
        ingredients: 'Red Bell Peppers, Tomatoes, and Low Fat Milk Blended Together with Seasonings',
        allergens: 'Gluten Free & Organic',
        imgSrc: 'RoastedRedPepperSoup'
      },  
      {
        name: 'BROCCOLI CHEDDAR',
        ingredients: 'A Creamy Mixture of Broccoli, Onions, Butter, and Cheddar Cheese',
        allergens: 'Gluten Free',
        imgSrc: 'BroccoliCheddarSoup'
      },  
      {
        name: 'CREAMY BUTTERNUT SQUASH',
        ingredients: 'Butternut Squash Soup as a Creamy Base with Spices',
        allergens: 'Dairy Free, Gluten Free, & Organic',
        imgSrc: 'ButternutSoup'
      },
      {
        name: 'LENTIL',
        ingredients: 'Green Lentils, Celery, Carrots, Potatoes and Spices',
        allergens: 'Dairy Free, Gluten Free, & Organic',
        imgSrc: 'LentilSoup'
      },    
      {
        name: 'VEGETABLE LENTIL',
        ingredients: 'Onions, Carrots, Celery, Green Lentils, Potatoes, Tomatoes, Green Beans, and Spices',
        allergens: 'Dairy Free, Gluten Free, & Organic',
        imgSrc: 'LentilVegetableSoup'
      },
      // {
      //   name: 'CHICKEN & WILD RICE',
      //   ingredients: 'Chicken in a Creamy Chicken Broth with Carrots, Celery, Green Onions, Cream, and Spices',
      //   allergens: 'Gluten Free & Organic',
      //   imgSrc: ''
      // },    
      {
        name: 'CREAMY TOMATO BASIL', 
        ingredients: 'Carrots, Celery, Onions, Tomatoes, and Sweet Basil Creamed Together',
        allergens: 'Gluten Free',
        imgSrc: 'CreamyTomatoBasilSoup'
      }
    ]
    let drinks = [
      {name: 'CHAI ALMOND LATTE: 16 OZ', price: '$4.50', imgSrc: 'Chai'},
      {name: 'COFFEE ORGANIC BLACK', price: '$4.50', imgSrc: 'BlackCoffee'},
      {name: 'DANDY BLEND TEA: 16 OZ', price: '$4.50', imgSrc: 'CoffeeDandy'},
      {name: 'MUD WATER LATTE: 16 OZ', price: '$6.50', imgSrc: 'CoffeeMudWtr'},
      {name: 'BOTTLED WATER', price: '$1.50', imgSrc: ''},
      {name: 'HERBAL TEA: 16 OZ', price: '$4.50', imgSrc: ''},
      {name: 'SUPERFOOD HOT COCOA(COMING)', price: '$'},

    ]
    let miscItems = [
      {
        name: 'Nut Butters'
      }
    ]
    return {
      bowls,
      blasts,
      soups,
      drinks
    }
  }
}
</script>

<style>

</style>