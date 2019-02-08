<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    </br>
    <div>
      <label for="finishedReading">
        Finished Reading
        <input type="checkbox" v-model="bookData.finishedReading"></input>
      </label>
    </div>
    </br>
    <label for="borrowed">
      borrowed
      <input type="radio" v-model="bookData.ownership" value="borrowed"></input>
    </label>
    <label for="bought">
      bought
      <input type="radio" v-model="bookData.ownership" value="bought"></input>
    </label>
    </br>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    }
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
