<template>
  <form class="" action="#" method="post" @submit="bookSubmit(bookTitle,bookAuthor).preventDefault()">
    <input v-model="bookTitle" type="text" name="title" value="" placeholder=" Book Title" />
    <input v-model="bookAuthor" type="text" name="author" value="" placeholder="Book Author" />
    <button type="submit" name="button">Add Book</button>
  </form>
</template>
<script>
export default{
  name: "BookForm",
  props: ['books'],
  data () {
    bookTitle = '',
    bookAuthor = ''
  },
  methods: {
    bookSubmit(bookTitle,bookAuthor){
      /* This.$emit creates an event that can be used elsewhere,
      So when this event triggers elsewhere, it knows to
      grab the bookTitle and bookAuthor */
      this.$emit('addBook', bookTitle, bookAuthor);
    }
  }
}
</script>
<style></style>
