<template>
  <div class='books'>
    <Book
      :key="book.id" 
      v-for="book in books"
      :title="book.title"
      :image="book.image"
      :authors="book.authors"
      :publisher="book.publisher"
      :publishDate="book.publishedDate"
      :id="book.id"
    />
  </div>
</template>

<script>
import Book from './components/Book';
import { Allbooks } from './data.js'; 

export default {
  name: 'App',
  setup() {
    const books = Allbooks  

    return {
      books
    }
  },
  components: {
    Book
  }
}
</script>

<style>
body{
 background-color: rgb(234, 238, 241);
}

#app{
  width: 95%;
  max-width: 1100px;
  margin: 50px auto;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.books{
  display: grid;
  place-content: center;
  margin-top: 10px;
  grid-gap: 15px;
}

.buttons {
  display: flex;
  gap: 5%;
  justify-content: center;
  margin-top: 30px;
}

.buttons button {
  padding: 5px 20px;
  background-color: #6796ec;
  border: none;
  color: white;
}

.center {
  text-align: center;
  display: block;
}

@media (min-width: 600px) {
  .books {
    grid-template-columns: 1fr 1fr;
    grid-gap: 15px;
  }
}

@media (min-width: 930px) {
  .books {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
</style>
