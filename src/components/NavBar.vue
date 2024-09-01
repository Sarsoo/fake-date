<script setup>

</script>

<template>
  <div class="bottom-nav">
    <a href="#" class="active">
      <span class="icon"><span class="material-icons">home</span></span>
<!--      <span class="text">Home</span>-->
    </a>
    <a href="#">
      <span class="icon"><span class="material-icons">diamond</span></span>
<!--      <span class="text">Search</span>-->
    </a>
    <a href="#">
      <span class="icon"><span class="material-icons">chat</span></span>
<!--      <span class="text">Add</span>-->
    </a>
    <a href="#">
      <span class="icon"><span class="material-icons">person</span></span>
<!--      <span class="text">Favorites</span>-->
    </a>
    <a href="#">
      <span class="icon"><span class="material-icons">settings</span></span>
<!--      <span class="text">Profile</span>-->
    </a>
  </div>
</template>

<style scoped>
.bottom-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: #333;
  box-shadow: 0 -1px 5px rgba(0, 0, 0, 0.2);
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 10px 0;
}

.bottom-nav a {
  text-align: center;
  flex-grow: 1;
  color: white;
  text-decoration: none;
  font-size: 14px;
}

.bottom-nav a .icon {
  display: block;
  font-size: 24px;
  margin-bottom: 5px;
}

.bottom-nav a.active {
  color: #ff5722;
}
</style>