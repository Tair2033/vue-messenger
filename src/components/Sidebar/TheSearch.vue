<template>
  <div class="search-wrapper">
    <input class="search-input" id="search-input" placeholder="Search">
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.search-wrapper {
  margin-top: 20px;
  padding: 0.5rem;
  display: flex;
  justify-content: center;
  border-top: 1px solid #eae9e9;
  border-bottom: 1px solid #eae9e9;
}

.search-input {
  border: 2px solid #e0e0e0;
  background-color: #f9f9f9;
  height: 36px;
  border-radius: 25px;
  width: 100%;
  outline: none;
  padding: 0.2em 1em;
  font-family: 'Lato', sans-serif;
  color: #555;
}

.search-input:focus {
  border-color: green;
}
</style>