<!-- <template>
<HelloWorld msg="Welcome to Your Vue.js App"/>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue';
export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script> -->

// Add your code here
<!-- 
<template>
  <div class="p-4">
    <h1 class="text-2xl font-bold mb-4">Food</h1>
    <p class="mb-2">The toggle button on the component emits an event to the parent "App.vue". The favorite status is modified in "App.vue", and the updated status is sent back to the component so that the image is toggled to reflect the favorite status.</p>
    <p class="mb-6">The result looks exactly like before, but now the favorite status is modified where it should be in "App.vue" instead of in the "FoodItem.vue" component.</p>
    <div id="wrapper" class="flex flex-wrap">
      <FoodItem
        v-for="x in foods"
        :key="x.name"
        :food-name="x.name"
        :food-desc="x.desc"
        :is-favorite="x.favorite"
        @toggle-favorite="receiveEmit"
        class="border border-dashed border-black flex-basis-120px m-2 p-2 bg-green-200"
      />
    </div> 
  </div>
</template>

<script>
import FoodItem from './components/FoodItem.vue';
export default {
  name: 'App',
  data() { 
    return {
      foods: [
        { name: 'Apples', desc: 'Apples are a type of fruit that grow on trees.', favorite: true },
        { name: 'Pizza', desc: 'Pizza has a bread base with tomato sauce, cheese, and toppings on top.', favorite: false },
        { name: 'Rice', desc: 'Rice is a type of grain that people like to eat.', favorite: false },
        { name: 'Fish', desc: 'Fish is an animal that lives in water.', favorite: true },
        { name: 'Cake', desc: 'Cake is something sweet that tastes good.', favorite: false }
      ]
    };
  },
  methods: {
    receiveEmit(foodId) {
      let foundFood = this.foods.find(food => food.name === foodId);
      foundFood.favorite = !foundFood.favorite;
    }
  },
  components: {
    FoodItem
  }
}
</script>

<style scoped>
  .flex-basis-120px {
    flex-basis: 120px;
  }
</style> -->

//Books portion

<template>
  <div class="flex">
    <BookItem v-for="book in books" :key="book.name" :book-name="book.name" :book-desc="book.description"
      :is-favourite="book.isFavourite" @item-fav="addItem" />
    <div>
      <h2 class="text-xl">Favourite Books</h2>
      <p class="text-md" v-for="fbook in favBooks">{{ fbook }}</p>
    </div>
  </div>


</template>
<script>
import BookItem from './components/BookItem.vue';
export default {
  name: 'App',
  data() {
    return {
      books: [
        {
          "name": "To Kill a Mockingbird",
          "description": "A novel by Harper Lee published in 1960, widely studied in literature classes for its themes of racial injustice and moral growth.",
          "isFavourite": true
        },
        {
          "name": "1984",
          "description": "A dystopian social science fiction novel and cautionary tale, written by the English writer George Orwell.",
          "isFavourite": false
        },
        {
          "name": "The Great Gatsby",
          "description": "A 1925 novel written by American author F. Scott Fitzgerald that follows a cast of characters living in the fictional towns of West Egg and East Egg.",
          "isFavourite": true
        },
        {
          "name": "The Catcher in the Rye",
          "description": "A novel by J. D. Salinger, partially published in serial form in 1945–1946 and as a novel in 1951. It has been translated into almost all of the world's major languages.",
          "isFavourite": false
        },
        {
          "name": "Pride and Prejudice",
          "description": "A romantic novel of manners written by Jane Austen in 1813. The novel follows the character development of Elizabeth Bennet, the dynamic protagonist of the book.",
          "isFavourite": true
        }
      ],
      favBooks: [

      ],
    }
  },
  methods: {
    addItem(bName) {
      this.favBooks.push(bName);
    }
  },
  components: {
    BookItem
  }
}
</script>
