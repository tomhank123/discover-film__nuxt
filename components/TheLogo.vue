<template>
  <img class="TheLogo" src="~/assets/img/logo.svg" height="18" />
</template>

<style>
.TheLogo {
  transform: rotateY(560deg);
  animation: turn 3.5s ease-out forwards 1s;
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
