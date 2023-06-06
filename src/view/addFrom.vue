<template>
  <div>
    <form class="shadow-md rounded px-8 pt-6 pb-8 mb-4" @submit.prevent>
      <div class="mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="title">
          Title
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="title" type="text" :value="info.title" @input="(e) => this.info.title = e.target.value" placeholder="Title"
          required />
      </div>
      <div class="mb-2">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="author">
          Author
        </label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
          id="author" :value="info.author" @input="(e) => this.info.author = e.target.value" type="text"
          placeholder="Author" required />
      </div>
      <div class="mb-6">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="isbn">
          ISBN#
        </label>
        <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight" id="isbn"
          :value="info.isbn" @input="(e) => this.info.isbn = e.target.value" placeholder="ISBN#" required />
      </div>
      <div class="flex items-center justify-between">
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded m-auto" type="submit"
          @click="sendItem">
          AddBook
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      info: {
        title: '',
        author: '',
        isbn: ''
      }
    }
  },
  methods: {
    sendItem() {
      if (title.value && author.value && isbn.value) {
        let id = Math.floor(Math.random() * 9999)
        let item = {
          title: this.info.title,
          author: this.info.author,
          isbn: this.info.isbn,
          id: id
        }
        this.$emit('addItemHandler', item)
        this.info.title = " "
        this.info.author = " "
        this.info.isbn = " "
      }
    }
  }
};
</script>

<style></style>
