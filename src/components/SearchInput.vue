<template>
    <div class="searchWrapper">
        <div class="search">
            <input type="text" name="search" v-model="searchValue" @input="handleInput" />
        </div>
    </div>
</template>

<script>
export default {
  name: 'searchInput',
};
</script>

<style lang="scss" scoped>
.searchWrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0;
  padding: 30px;
  width: 100%;
}
.search {
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  width: 250px;
  input {
    height: 30px;
    border: 0;
    border-bottom: 1px solid black;
    background: none;
  }
}
</style>
