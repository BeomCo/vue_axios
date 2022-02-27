<template>
  <div class="container">
    <title :title="mainTitle" />
    <Search />
    <listWrap />
    <Modal />
  </div>
</template>

<script>
import axios from "axios";
import Title from "./components/TitleCp.vue";
import Search from "./components/SearchCp.vue";
import ListWrap from "./components/ListWrap.vue";
import Modal from "./components/ModalCp.vue";

export default {
  name: 'App',
  components: {
    Title,
    Search,
    ListWrap,
    Modal,
  },
  data(){
    return{
      mainTitle : "푸드 하우스",
      foods : [],
      food : {},
      isSelected : false,
      searchFoods : []
    }
  },
  async created() {
    const { data } = await axios.get('/json/food.json');
    console.log(data);
    this.foods = data;
    this.searchFoods = data;
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
