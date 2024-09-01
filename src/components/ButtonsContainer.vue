<script setup>

</script>

<template>
  <div class="buttons">
    <div class="btn no">✘</div>
    <div class="btn yes">✔</div>
  </div>
</template>

<style scoped>

.buttons {
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-around;
  padding: 0 20px;

  z-index: 100;
}

.btn {
  width: 60px;
  height: 60px;
  background-color: white;
  border: 2px solid #ccc;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  color: #666;
  cursor: pointer;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s, border-color 0.3s;
}

.btn:hover {
  background-color: #f5f5f5;
  border-color: #bbb;
}

.btn:active {
  transform: scale(0.9);
}

.btn.no {
  color: #ff3b30;
}

.btn.yes {
  color: #4cd964;
}

</style>