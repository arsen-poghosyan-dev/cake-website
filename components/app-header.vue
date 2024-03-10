<template>
  <div class="app-header">
    <div class="app-container">
      <div class="app-header-body">

        <div class="app-header--logo">
          <img src="/logo.png">
        </div>

        <div class="app-header-item" :class="{isMenuOpen: isMenuOpen}" >
          <div class="app-header-item--menu">
            <a href="">Mer Masin</a>
            <a href="">Torter</a>
            <a href="">Contact</a>
          </div>
          <div class="app-header-item--social-icons">
            <a href="#">
              <i class="fa-solid fa-house app-header-icons1"></i>
            </a>
            <a href="#">
              <i class="fa-brands fa-facebook app-header-icons1"></i>
            </a>
            <a href="#">
              <i class="fa-brands fa-instagram app-header-icons1"></i>
            </a>
            <a href="#">
              <i class="fa-brands fa-tiktok app-header-icons1"></i>
            </a>
          </div>
        </div>

        <div class="app-header-toggle" :class="{isMenuOpen: isMenuOpen}"  @click="isMenuOpenClick">
          <i class="fa-solid fa-bars"></i>
        </div>

      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default  {
  name: 'app-header',
  setup() {
    const isMenuOpen = ref<boolean>(false)

    const isMenuOpenClick = () => {
      isMenuOpen.value = !isMenuOpen.value
    }

    return {
      isMenuOpen,
      isMenuOpenClick
    }
  }
}
</script>

<style >
.app-header{
  position: fixed;
  background: #ffffff;
  top: 0;
  width: 100%;
  border-bottom: 3px solid burlywood;
}
.app-header-body {
  height: 65px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.app-header--logo {
  img {
    width: 100%;
    max-width: 160px;
  }
}

.app-header-item {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
}
.app-header-item--menu {
  margin:  0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
  a {
    font-weight: 600;
    font-size: 19px;
    color: black;
    text-decoration: none;
    border-bottom: 2px solid black;
    transition: all 800ms;
    margin-left: 20px;
  }
  a:hover{
    font-weight: 600;
    color: burlywood;
    border-bottom: 2px solid burlywood;
    transition: all 300ms;
  }
}
.app-header-item--social-icons {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row;
  a {
    color: burlywood;
    font-size: 20px;
    display: block;
    padding: 0 5px;
    transition: all 800ms;
  }
  a:hover{
    color: black;
    transition: all 300ms;
  }
}

.app-header-toggle {
  cursor: pointer;
  color: burlywood;
  font-size: 20px;
  display: none;
  padding: 0 5px;
  transition: all 800ms;
}
.app-header-toggle.isMenuOpen {
  transform: rotate(90deg);
}
@media only screen and (max-width: 730px) {
  .app-header-toggle {
    display: block;
  }

  .app-header-item {
    position: fixed;
    background: #ffffff;
    top: 70px;
    left: 0;
    right: 0;
    bottom: 0;
    translate: -100% 0;
    transition: all 600ms;
    justify-content: flex-start;
    align-items: center;
    flex-direction: column;
  }
  .app-header-item.isMenuOpen {
    translate: 0 0;
  }

  .app-header-item--menu {
    margin: 30px auto;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    a {
      text-align: center;
      margin-bottom: 15px;
    }
  }



}


</style>