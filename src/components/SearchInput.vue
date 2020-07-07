<template>
    <div class="searchWrapper">
        <div class="search">
            <input
            type="text"
            id="search"
            name="search"
            v-model="searchValue"
            @input="handleInput" />
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
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  width: 250px;
  input {
    height: 30px;
    border: 0;
    text-align: center;
    border-bottom: 1px solid rgb(209, 208, 208);
    color: rgb(209, 208, 208);
    background: none;
    transition: box-shadow .5s;
  }
  input:focus{
      box-shadow: 0 10px 20px -8px rgba(209, 209, 209, .3)
  }
}
</style>
