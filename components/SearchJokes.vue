<template>
  <form @submit.prevent="onSubmit">
    <input class="search_bar" type="text" v-model="text" placeholder="Search Dad Jokes" />
    <input class="search_input" type="submit" value="Search Joke" />
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    },
  },
};
</script>

<style scoped>
.search_bar {
  width: 150px;
  border: none;
  outline: none;
  font-size: 18px;
}

.search_bar:focus {
  border-bottom: 2px solid #8a2ce2;
  width: calc(100% - 150px);
  animation-name: example;
  animation-duration: 0.6s;
}

@keyframes example {
  0% {
    width: calc(25% - 150px);
  }
  100% {
    width: calc(100% - 150px);
  }
}

.search_input {
  color: #8a2ce2;
  border-radius: 5px;
  border: 1px solid #8a2ce2;
  outline: none;
  font-size: 18px;
  font-weight: 800;
  background-color: transparent;
  padding: 0.3rem 1rem;
}

.search_input:hover {
  color: #fff;
  border: 1px solid #8a2ce2;
  background-color: #8a2ce2;
  cursor: pointer;
}
</style>