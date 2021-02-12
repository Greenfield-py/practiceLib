<template>
  <div>
    <div class="elCard" :body-style="{ padding: '0px' }">
      <div class="front">
        <img
          src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"
          class="image"
        />
        <div style="padding: 14px;">
          <span>Название</span>
          <el-row>
            <small>Автор: </small>
          </el-row>
        </div>
      </div>
      <div class="back">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Vel rerum
        quisquam ut ipsum adipisci ad incidunt porro ducimus voluptatem culpa.
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.elCard {
  width: 235px;
  height: 310px;
  perspective: 1000px;
}

.front,
.back {
  transition: 1s;
  position: absolute;
  z-index: 2;
  display: flex;
  backface-visibility: hidden;
  flex-direction: column;
  box-shadow: 0 2px 12px 0 rgb(0 0 0 / 10%);
  border-radius: 4px;
  overflow: hidden;
  width: inherit;
  height: inherit;
}

.front {
  background: white;
  transition: 1s;
  position: absolute;
  z-index: 2;
  justify-content: center;
}

.back {
  transform: rotateY(180deg);
  z-index: -2;
  padding: 10px;
}

.elCard:hover .front {
  transform: rotateY(-180deg);
}

.elCard:hover .back {
  transform: rotateY(0deg);
}
</style>
