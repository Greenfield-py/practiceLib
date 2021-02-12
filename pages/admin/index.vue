<template>
  <el-container class="pageWrapper">
    <el-header><h1>Добавить книгу</h1></el-header>
    <el-main>
      <el-form @submit.native.prevent="onSubmit">
        <el-input
          class="mb"
          placeholder="Введите название книги"
          v-model="name"
        ></el-input>
        <el-input
          class="mb"
          placeholder="Введите автора"
          v-model="autorName"
        ></el-input>
        <el-input
          class="mb"
          placeholder="Введите жанр"
          v-model="janre"
        ></el-input>
        <el-input
          class="mb"
          type="textarea"
          :rows="4"
          resize="none"
          placeholder="Введите описание"
          v-model="description"
        >
        </el-input>
        <el-upload
          class="mb"
          drag
          ref="upload"
          action="https://jsonplaceholder.typicode.com/posts/"
          :on-change="handleImageChange"
          :auto-upload="false"
        >
          <i class="el-icon-upload"></i>
          <div class="el-upload__text">
            Перетащите картинку
            <em>или нажмите</em>
          </div>
          <div class="el-upload__tip" slot="tip">
            файлы с расширением jpg/png
          </div>
        </el-upload>
        <el-button type="success">
          Сохранить
        </el-button>
      </el-form>
    </el-main>
  </el-container>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      autorName: "",
      janre: "",
      image: null,
      description: ""
    };
  },
  methods: {
    handleImageChange(file, fileList) {
      this.image = file.raw;
    }
  }
};
</script>

<style scoped>
.pageWrapper {
  margin: 20px 50px 0;
}
.mb {
  margin-bottom: 15px;
}
form {
  width: 400px;
}
</style>
