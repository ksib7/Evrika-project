<template>
  <transition name="fade">
    <div v-if="isPreloaderVisible" class="preloader">
      <h2>Добро пожаловать!</h2>
      <div class="preloader__circles">
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
        <div class="preloader__circles__circle"></div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      isPreloaderVisible: true,
    };
  },

  mounted() {
    this.hidePreloader();
  },

  methods: {
    hidePreloader() {
      setTimeout(() => {
        this.isPreloaderVisible = false;
      }, 1000);
    },
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Neonderthaw&family=Roboto+Condensed&family=Source+Sans+Pro:wght@200;400;600&display=swap");

.preloader {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -ms-flex-line-pack: center;
  align-content: center;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: white;
  z-index: 111;
}

.preloader__circles {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  gap: 20px;
  margin-top: 20px;
}

.preloader__circles__circle {
  width: 25px;
  height: 25px;
  background-color: grey;
  border-radius: 50%;
  -webkit-animation-name: scaleIn;
  animation-name: scaleIn;
  -webkit-animation-duration: 1.7s;
  animation-duration: 1.7s;
  -webkit-animation-name: scaleOut;
  animation-name: scaleOut;
  animation-duration: 1.7s;
  -webkit-transform: scale(0);
  -ms-transform: scale(0);
  transform: scale(0);
}

.preloader__circles__circle:nth-child(1) {
  -webkit-animation-delay: 0s;
  animation-delay: 0s;
}

.preloader__circles__circle:nth-child(2) {
  -webkit-animation-delay: 0.1s;
  animation-delay: 0.1s;
}

.preloader__circles__circle:nth-child(3) {
  -webkit-animation-delay: 0.2s;
  animation-delay: 0.2s;
}

.preloader__circles__circle:nth-child(4) {
  -webkit-animation-delay: 0.3s;
  animation-delay: 0.3s;
}

.preloader__circles__circle:nth-child(5) {
  -webkit-animation-delay: 0.4s;
  animation-delay: 0.4s;
}

.preloader__circles__circle:nth-child(6) {
  -webkit-animation-delay: 0.5s;
  animation-delay: 0.5s;
}

.preloader__circles__circle:nth-child(7) {
  -webkit-animation-delay: 0.6s;
  animation-delay: 0.6s;
}

.preloader__circles__circle:nth-child(8) {
  -webkit-animation-delay: 0.7s;
  animation-delay: 0.7s;
}

.preloader__circles__circle:nth-child(9) {
  -webkit-animation-delay: 0.8s;
  animation-delay: 0.8s;
}

.preloader__circles__circle:nth-child(10) {
  -webkit-animation-delay: 0.9s;
  animation-delay: 0.9s;
}

.fade-enter-active,
.fade-leave-active {
  -webkit-transition: opacity 0.5s;
  -o-transition: opacity 0.5s;
  transition: opacity 0.5s;
}

.preloader h2 {
  font-family: "Source Sans Pro";
  font-weight: 600;
  font-size: 62px;
  margin: 0 auto;
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;
  background-image: -o-linear-gradient(134deg, #ffc857 0%, #3e2f5b 74%);
  background-image: linear-gradient(316deg, #ffc857 0%, #3e2f5b 74%);
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

@-webkit-keyframes scaleOut {
  0% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }

  100% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }
}

@keyframes scaleOut {
  0% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }

  100% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }
}

@-webkit-keyframes scaleIn {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }

  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}

@keyframes scaleIn {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }

  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}
</style>
