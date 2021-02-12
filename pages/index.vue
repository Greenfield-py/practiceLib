<template>
  <el-container class="mainContainer">
    <el-header>
      <h1>Библиотека</h1>
    </el-header>
    <el-row class="mb"
      ><el-select v-model="janreValue" placeholder="Жанр">
        <el-option
          v-for="janre in janres"
          :key="janre"
          :label="janre"
          :value="janre"
        >
        </el-option>
      </el-select>
      <el-select v-model="autorValue" placeholder="Автор">
        <el-option
          v-for="autor in autors"
          :key="autor"
          :label="autor"
          :value="autor"
        >
        </el-option> </el-select
    ></el-row>
    <div :gutter="20">
      <el-col
        class="mb"
        v-for="(card, index) in 10"
        :key="index"
        :xs="12"
        :sm="8"
        :md="6"
        :lg="6"
      >
        <Card />
      </el-col>
    </div>
  </el-container>
</template>

<script>
import Card from "@/components/Card";
export default {
  components: {
    Card
  },
  data() {
    return {
      janres: ["adventure", "vovas_adventure"],
      janreValue: "",

      autors: ["vova", "vovaFather"],
      autorValue: ""
    };
  }
};
</script>

<style scoped>
h1 {
  text-align: center;
}
.mainContainer {
  margin: 50px 30px 0;
}
.mb {
  margin-bottom: 15px;
}
</style>
