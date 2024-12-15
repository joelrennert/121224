<template>
  <div class="overlay">
    <div class="menu" :class="{ clicked: isclicked }" @click="toggleContainer">
      Click anywhere to begin
    </div>
    <transition name="fade">
      <div class="container" v-show="showContainer">
        <div class="top">
          <div class="leftContainer">
            <div class="left">welcome to my website joel</div>
          </div>
          <div class="midContainer">
            <div class="mid">yes</div>
          </div>
          <div class="rightContainer">
            <div class="right">🍄</div>
          </div>
        </div>
        <div class="mainContent">main content</div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isClicked: false,
      showContainer: false
    }
  },
  methods: {
    toggleContainer() {
      this.isClicked = !this.isClicked
      this.showContainer = !this.showContainer
    }
  }
}
</script>

<style scoped>
.overlay {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  padding: 40px;
  z-index: 2;
}

.menu {
  position: fixed;
  width: 100%;
  height: 100%;
  padding: 10px;
  font-size: 25px;
  transition: transform 0.2s ease;
  transform-origin: center;
  top: 0;
  font-size: 1rem;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.container {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(15px);
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  width: 95vw;
  height: 90vh;
  z-index: 1;
  gap: 5px;
  border-radius: 20px 30px 20px 30px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.top {
  display: flex;
  justify-content: center;
  align-items: center;
  border-top-left-radius: 20px;
  border-bottom-right-radius: 20px;
  border-top-right-radius: 20px;
  width: 100%;
}

.leftContainer {
  background-color: rgba(255, 255, 255, 0.321);
  border-top-left-radius: 20px;
  width: 50%;
}

.midContainer {
  width: 100%;
}

.rightContainer {
  border-top-right-radius: 30px;
  background-color: rgba(255, 255, 255, 0.321);
}

.left {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  background-color: rgba(255, 255, 255, 0.546);
  border-top-left-radius: 20px;
  border-bottom-right-radius: 20px;
  width: 100%;
}

.mid {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  flex-grow: 1;
  background-color: rgba(255, 255, 255, 0.321);
}

.right {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  padding-right: 20px;
  background-color: rgba(255, 255, 255, 0.171);
  border-top-right-radius: 30px;
  border-bottom-left-radius: 30px;
}

.mainContent {
  padding: 20px;
}
</style>
