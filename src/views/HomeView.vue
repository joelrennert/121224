<script setup>
import SquareNoAnimation from "../components/SquareNoAnimation.vue";
</script>

<template>
  <main>
    <div class="container">
      <SquareNoAnimation
        v-for="n in 50"
        :key="n"
        :style="{
          transform: `scale(${5 - n * 0.01}) rotate(${n * 12424}deg) translate(${n * 2}px, ${n * 2}px)`,
        }"
        :class="{ square: true }"
      />
    </div>
  </main>
</template>

<style scoped>
@keyframes square-animation {
  0% {
    background-position: 0% 0%;
  }
  50% {
    background-position: 200% 200%;
  }
  100% {
    background-position: 0% 0%;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.square {
  position: absolute;
  top: 50%;
  left: 50%;
  transform-origin: center;
  padding: 30px;
  opacity: 1;
  background: linear-gradient(135deg, #fcb04595, #fd1d1d7c 40%, #8463ae94);
  background-size: 30% 30%;
  animation:
    square-animation 40s ease-in-out infinite,
    fadeIn 2s ease-in forwards;
  transition:
    transform 0.5s ease,
    background 0.5s ease,
    background-size 0.7s ease,
    box-shadow 0.5s ease;
}

.square:hover {
  background: linear-gradient(135deg, #fcb04595, #fd1d1d7c 40%, #8463ae94);
  background-size: 35% 35%;

  cursor: pointer;
}

.square:hover + .square,
.square:hover ~ .square,
.square:active + .square,
.square:active ~ .square {
  transform: scale(1.05);
  background: linear-gradient(135deg, #fcb04595, #fd1d1d7c 40%, #8463ae94);
  background-size: 40% 40%;
}

.square:active {
  background: linear-gradient(140deg, #fcb04595, #fd1d1d7c 40%, #8463ae94);
  background-size: 30% 30%;
}

.container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

main {
  width: 100%;
  height: 100vh;
  font-family: "IBM Plex Mono";
  color: #333;
  background: linear-gradient(90deg, #8463ae94, #fd1d1d7c 40%, #fcb04595);
  background-size: 100% 300%;
  /* animationo: gradient-shift 10s ease-in-out infinite; */
}

@keyframes gradient-shift {
  0%,
  100% {
    background-position: 0% 0%;
  }
  50% {
    background-position: 100% 100%;
  }
}

main::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  opacity: 0.45;
  z-index: -1;
}
</style>
