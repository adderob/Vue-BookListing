<template>
  <div>
    <h1>{{ title }}</h1>
    <ul>
      <book-form @addBook="appendBook" />
      <book-item v-for="book in books" :book="book" />
    </ul>
  </div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';

  export default {
    name: "BookList",
    components: {
      BookItem,
      BookForm},
    methods: {
      appendBook(bookTitle,bookAuthor){
        this.books.push({ title: bookTitle, author: bookAuthor })
      }
    },
    data() {
      return {
        title: "All Books",
        books:
        [
          {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
          {title: 'American Gods', author: 'Neil Gaiman'},
          {title: 'Amusing Ourselves to Death', author: 'Neil Postman'}
        ]
      }
    }
  }
</script>

<style>
h1, h2 {
  font-weight: normal;
}
ul{
  list-style-type: none;
  padding: 0;
}
</style>
